---
layout: post
title: Green And Gold
tags: Green eZ80 MSX Yellow
---

I have not had the privilege of a lot of free time over the last few months, which limited my ability to explore and experiment with the eZ80 RC2014/RCBus system.  And with so many things on the backlog....

But recently I have come into the possession of a little more time.  And did manage to at least get one idea moving forward.

<img src="{{ site.baseurl }}/assets/images/pacman-ez80.jpg"/>

### Zilog turtles all the way down

One of the original inspiration for developing the eZ80 CPU module was to potentially use it as a 2nd CPU for the Yellow MSX system -- something similar to how the Turbo MSX used the [Zilog R800 CPU](https://en.wikipedia.org/wiki/R800).  The Turbo MSX would switch between the 2 processors - using the faster processor for newer software, but switching to the Z80 for compatibility with older software and games.

The eZ80 and the R800 are not compatible processors though.  And further, to modify the hardware design of the Yellow MSX and eZ80 Module to enable the cpu switching, via software, is certainly doable, but requires a fair bit of work (and time).

But then I had a brainwave!  I wondered - is the eZ80 fast enough to 'emulate' a Z80?  Could it interpret all the Z80 opcodes fast enough (assuming a Z80 running around the 3.5Mhz mark) and achieve the required level of compatibility.  Could it run MSX game cartridges using this interpretation approach?  Could I get the original PACMAN game to run using the eZ80 as the CPU?

The eZ80 is much faster than the R800, although certainly not as fast as modern 32/64Bit CPUs.  (Modern PC can easily emulate Z80 based system in your browser).  The eZ80 is still an 8bit CPU -- it's not super fast at all.  Could it work?  Would an emulator be able to achieve the equivalent performance of a 3.5MHz Z80 CPU?

### What about the eZ80's Z80 compatibility mode?

You may be wondering why I did not utilise the eZ80's Z80 compatibility mode, to just run the code natively.  Well there are a few 'buts' with this option:

1. It's much faster - so if we attempt to run any original MSX code, it will run way too fast.  It may be possible to configure it to run 'slow' - not sure - but there are still other buts!
2. The eZ80 has some extra op-codes that the Z80 does not have.  If the Z80 encounters an opcode it does not recognise - it typically just ignores it and moves on.  Most software written for the Z80 would likely not have any such opcodes, but if any such opcode did exist in the software, through intention or not, the eZ80 will generate a `RST 00` (kind of like an exception) and effectively reboot itself.
3. Some Z80 'dud' instructions have been repurposed for the eZ80.  For example the instruction `ld d,d` - which is rather pointless - a kind of no-op - if encountered by the eZ80 will cause it to handle the next instruction differently.  So if some coder left such no-op instructions like these in their code, then the eZ80 will likely crash.
4. The eZ80 is not just a CPU - its a (SOC) system on chip.  It has ROM/RAM and its own hardware ports.  The I/O ports from $0000 to $00FF are reserved for these on-chip systems.  Original MSX (and most other Z80 code) - assumes a different configuration for I/O access.  This is the biggest hurdle with having the eZ80 run Z80 code.  Any I/O (that is access to the Video, Sound and other hardware) will invariably not work.  The code would need to be modified to run successfully on an eZ80 CPU directly.  So no PACMAN on the eZ80 natively.

### eZ80 driving the Yellow MSX system

Just this weekend, I finally managed to get my Yellow MSX system to boot with the eZ80 CPU emulating a Z80.

Perhaps a more accurate way to describe the developed solution is not so much as 'emulating', but rather as 'interpreting'.

I will need to write another post describing how the code works - and the tricks employed.  But it was quite a cool thing to have my MSX system boot up with the eZ80.  I have yet to do any performance measurements - it seems to be fast enough - PACMAN and SALAMANDA games play just fine.  Sound is synced and graphics are smooth.  These are not particularly demanding games though.  I need to test with some MSX2 games..

The emulated Z80 is not 'cycle' accurate.  Some instructions may be quicker than a Z80 and others slower.

### More to do

The emulator code for the eZ80 is sitting on a branch on the [github repo](https://github.com/dinoboards/ez80-for-rc/commits/dean/firmware-z80-emulator/)

There are still some Z80 opcodes not implemented yet.  And I need to do a lot more testing.

