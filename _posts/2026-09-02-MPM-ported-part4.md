---
layout: post
title: MP/M 2.1 running on the eZ80 - Part 4
tags: eZ80 Green RC2014 RCBUS CPM

---

### It Works!

As mentioned in the last post on this subject, I have been attempting to port Digital Research's multi-user operating system MP/M II to the eZ80 system. It proved to be a quite challenge - and after a few grueling weeks of coding, cursing and pondering loops - I finally managed to get a stable version of MP/M II working on my system.  I can run MP/M PRL programs (and compatible CP/M programs) concurrently.  With the HDMI for RC module and a compatible USB keyboard plugged into the USB for RC module, I can actually have 2 user sessions running concurrently.

### Memory Challenge

MP/M II (like the similar CP/M 3.0) had a recommended memory requirement of more than 64K of RAM. As the Z80 can only directly access 64K of RAM, MP/M expected supporting hardware connected between the CPU and the memory to perform 'bank switching' and allow the operating system to use more than the limited 64K.

> MP/M II could actually be configured to operate with just 64K of RAM - but the amount of memory available for users and their programs was very limited.  This port is focused exclusively on supporting the version of MP/M that expects more than 64K of memory.  The eZ80 combined with the 2MB Linear Memory Module would allow in theory, the ability to run MP/M at its full memory capacity.

The bank switching system was required to be able 'switch' over sections of memory within the Z80's 64K address range to different actual memory stores.  Thereby, allowing the CPU to access more than the Z80's maximum memory of 64K - but with only a specific 64K range of memory accessible at any given time to the CPU.

This hardware switching of 'banks' needs to change the lower addressed memory of the Z80 to different banks of 48K while keeping the higher 16K unchanged.  With that, core parts of the operating system can operate in the higher 16K range, and the user programs would have their own unique 48K bank of RAM.  Additionally MP/M reserved the first 48K bank for other parts of the operating system.  So that would leave (if the machine had sufficient memory), up to 7 banks of 48K for running up to 7 concurrent user programs.

I could have utilised one of the RC2014/RCBus's external memory modules, like the RC2014 512K RAM/ROM module to enable the memory banking.  These large memory modules includes hardware support for bank switching.  This probably would have been the sensible option, but sensible I am not -- I wanted a more eZ80 pure option using just the 2MB Linear Memory module.

So I needed to figure out a way to implement a compatible memory model for MP/M II to operate in the eZ80's larger linear memory feature.

The plan was to use the eZ80's Z80 compatibility mode to present multiple 64K segments, one for each user program.  But how to make the top 16K of memory the same across each of the memory segments?  The eZ80, in its compatibility mode, only allows me to switch a full 64K of memory from one location to another.  There is no way to keep the top 16K of memory the same.  So to get things initially working I just made the code copy the top 16K of memory from one segment to another as a kind of simulated 'bank switch'.  This, not surprising at all, resulted in quite poor system performance.

Other ports of the eZ80 have used the on-chip RAM of the eZ80 to map over the top part of the 64K segment.  But for me there were 2 problems with this solution:

1. The eZ80 variant I use only has 8K of on-chip memory.  MP/M requires closer to 16K of RAM (depending on number of users, file handlers and other buffer settings).

2. I have already configured and expected the on-chip RAM to exist at a specific address.  The ROM based firmware, expects to access UART buffers and other system variables at a specific address (0x02E000 to 0x02FFFF).  If the on-chip memory was relocated to different memory addresses within the eZ80 16MB address space, the firmware would fail.

## Reduce memory requirement

So my first task, was to refactor the original code to require less code be placed in the upper page of memory.  There is a lot of code in the system that is designed to run in this upper common page - somewhere between 11K and 12K of code for the BDOS and XDOS subsystems.  My goal was to move this code out of this address space and run it elsewhere.  By converting the code to run under eZ80's ADL mode - it could be executed at any address in the eZ80's 16MB address space - yet still access the buffers, variables or other code/data in the current 'active' 64K segment.  Within this common code area, the original routines would be converted to be a simple shim routine that delegates to code mapped outside of the 64K segment.

So a lot the original BDOS/XDOS routines become nothing more that an eZ80's long jump instruction.  For example the routine that parses a filename and builds FCB structures is now:

<pre style="margin-left:1em; margin-right:1em;  padding:0px;line-height:1em">
<code style="font-size:0.8em">
  parsefilename:
	jp.lil	parsefilename_adl

</code>
</pre>

And the routine `parsefilename_adl` is positioned outside of the 64K memory segment and looks like this:


<pre style="margin-left:1em; margin-right:1em;  padding:0px;line-height:1em">
<code style="font-size:0.8em">
  parsefilename_adl:
	;BC = .(.filename,.fcb)
	push.s	bc
	call	getmx
	pop.s	hl
	ld.s	e,(hl)
	inc	hl
	ld.s	d,(hl)
	ex	de,hl
	...
	...
</code>
</pre>

Note the use of the *.s* suffix to instruct the CPU to access memory in the 16bit address of the current 64K memory segment.

It took a long long time - and I hit many issues and obscure bugs.  But eventually I converted as much code as I could from the standard Z80 mode to the eZ80 ADL mode running outside of the 64K segment.  I eventually got the footprint of this upper common area small enough to potentially fit within the 8K of on-chip RAM.

## 8K On-chip RAM relocating

But just because the code required could now fit within the on-chip RAM - I still had the problem that all the firmware code requires the on-chip ram to always be mapped to address 0x02E000 to 0x02FFFF.

Not all of the on-chip RAM is used by the firmware - it only requires a relative small amount - less than 500 bytes.  So there is about 7.5K available.  Thats enough that it can be shared by the firmware and MP/M.

If I wanted to use the on-chip RAM for MP/M's top common RAM - I would need to dynamically relocate it as required.  For example if MP/M is currently executing code within the user memory segment at 0x3Axxxx - I would need to move the on-chip RAM to the 0x3A page.  Thus the on-chip RAM would be at the address range 0x3AE000 to 0x3AFFFF.  And then when MP/M switches the current segment to say, 0x3Bxxxx, the on-chip RAM would need to be relocated appropriately; to the address range of 0x3BE000 to 0x3BFFFF.

The eZ80's onboard logic makes it trivial to change the RAM's address as required - just need to write the base address to an internal port.

But for all of the onboard firmware code, that handles interrupts, UART communications and other functions, the code requires and expects the RAM to be at the original address (0x02xxxx).

So how to share the RAM between the 2 systems?  I have to modify the firmware code to always relocate the RAM to the original address.  Now when the eZ80 processes an interrupt, the first thing it does is to 'claim' the on-chip RAM and relocate it back to 0x02xxxx.  Once claimed, it can then execute the original code.  And lastly, before it returns control back, it restores the location of the on-chip RAM to its previously addressed location.

Combined with careful reserving of the space within the on-chip RAM (eg: the top 500 bytes for firmware, with the rest available for MP/M) - I was able to achieve a true fast bank switching process compatible with MP/M.

### Stack Management

One point I noted in my last post, was the challenge of tracking the SPL register.

Within MP/M there is a lot of manipulation of the SPS (short stack pointer) register.  As the system switches from one process to another it needs to save the current SP value and restore it for the next process.  MP/M also has lots of special stack spaces for things such as interrupt handling. Additionally all MP/M operating systems calls (BDOS/XDOS) are executed with their own stacks.

As I begun the ADL code conversion, I needed to maintain a valid long stack pointer (SPL) register - mirroring the SPS changes that MP/M does to the SPL register.

> The eZ80 has 2 separate stack pointer registers - SPS (short stack pointer) and the SPL - (long stack pointer).  When the eZ80 is in ADL mode and executes stack operations (CALL, PUSH, POP, etc), it uses the SPL registers to track the 3 byte (24 bit value).

Initially I extended MP/M's *Process Descriptor* structure, adding an additional 3 bytes to track the relevant SPL values.  But extending the size of this structure broke the MPMSTAT application - and also cause some other buffers and data structures to be moved from their original addresses - this change may break other original MP/M programs.

I have since change the way I track the SPL register values.  The *Process Descriptor* structure has been restored to its original size and layout.  I created a new data structure that tracks just the SPL register for each process.  This should restore compatibility with original programs.

> Get the stack handling code a little wrong - and things might look like they are working - but at some point the stack might corrupt some critical bit of data or code - and then very unpleasant things happen.  An extremely difficult thing to debug.  Modern processes have protected memory features that can prevent or at least stop immediately when it attempts to do something unexpected - but for these older processors - its just allowed to happen.  Many curse words were discovered during this time!


### Code available

For those that have the eZ80 for RC kit and the associated modules, you can try out the MP/M port.  The assembled and compiled release is available at: [https://codeberg.org/dinoboards/ez80-for-rc/releases](https://codeberg.org/dinoboards/ez80-for-rc/releases).

Once you have a boatable CP/M system, you can simply type the command MPM to transition and start MP/M II.

The release includes copies of the original User and Programmers manual for MP/M.
