---
layout: post
title: MP/M 2.1 running on the eZ80
tags: eZ80 Green RC2014 RCBUS CPM

---

I have just pushed some new code for the eZ80 system to include an initial port of Digital Research's MP/M II operating system.

MP/M is an operating system that is mostly compatible with CP/M and provides for multiple users and multi-processes. It's similar to CP/M Plus with its ability to address more than 64K of memory by using memory banking.

To have an operating system, running on a small 8 bit micro, that could support multiple users and multiple processes at the start of the 1980s was pretty cool.

To start the operating system, I have created a loader that can be invoked from the existing CP/M 2.2 instance. Just run the `MPM` command (see the screen capture below) and now you are in MP/M 2.1.

I grabbed Digital Research's original code from <a href="http://www.cpm.z80.de/source.html" target="_newwindow">http://www.cpm.z80.de/source.html</a> and committed it to my git repo. I made sure to respect the author and date of creation.

<div style="text-align: center;">
  <a href="{{ site.baseurl }}/assets/posts/gitlogwithdir.png" target="_newwindow">
  <img src="{{ site.baseurl }}/assets/posts/gitlogwithdir.png" alt="git history including commit from 45 years ago" width="100%">
  </a>
  A commit in my repo of code from 45 years ago!
</div>

<br/>

Getting MP/M to work on my eZ80 has required me to undertake some learnings ...

Of course, I am not the first to do this. Perhaps the most interesting port of MP/M was done by Chris Brock. He has a port (for the Zilog eZ80 dev platform, I think). He did more than just run the original code - he has updated the original source code to take full advantage of the eZ80. He has a few brief notes on his approach over on the <a href="https://forum.vcfed.org/index.php?threads/help-with-new-mp-m-ii-bringup.1253776/#post-1460383" target="_newwindow">Vintage Computer Federation Forums</a> and published his code on <a href="https://github.com/cbrock487/eZ80-MPM" target="_newwindow">Github</a>.

I need to study his code. But before I go down the path of running an eZ80 updated version of MP/M, I wanted to start by getting the original code working as-is.

The build process I implemented, recompiles all the original Digital Research assembly code. The PLM based code for command line tools such as DIR and PIP are a little trickier to compile, so I have just committed the prebuilt images.

Some key highlights from my adventure in porting the system:

## Using Z88DK compiled CP/M apps

MP/M should be able to run standard CP/M .com programs, so I was a little surprised that my "hello world" app, compiled with Z88DK, produced a BDOS error.

On closer inspection, I think the library code in Z88DK detects that the application is running in a later version of CP/M and then calls a BDOS function to set the exit code of the program. But this BDOS call is not implemented in MP/M! I can work around this issue for the time being - but I might try and get the maintainers of Z88DK to see if they can fix this.

## Banking when you dont really have banks!

MP/M, like many systems that desire more than the 64K of addressable memory, employed the idea of "banking" the memory. The CPU can only see 64K at any one time, but the specific 64K of memory that's connected to the CPU can be changed. MP/M expects to be able to change the lower range of memory selected (changing it to another bank) and keep the top few kilobytes the same.

For the eZ80, we have the concept of MBASE, where we can tell the CPU, when running in Z80 compatibility mode, to address one full 64K page of memory. We can't use this technique to split within the 64K range. A technique others have used for porting MP/M to the eZ80 is to use the internal on-chip memory and configure it to be placed at the top of any given 64K memory range. But since I use this on-chip memory in my firmware, and given it's only 8K, I chose not to try this approach - at least for the time being.

Instead, I use a more brute force, low performance method. When MP/M requests a bank switch, I change the current MBASE to the 64K range associated with the requested bank, and also copy the top part of the RAM from the previous MBASE segment. So that means there is about a 13K memory copy (LDIR) performed every time the system needs to change banks. It's not so slow as to be useless (at least not yet, based on my limited testing) - but it works.

## Assembling a custom BIOS (BNKXIOS)

MP/M, like CP/M, is an operating system targeting the old Intel 8080 CPUs. It does not use any of the extended instructions that Zilog introduced in the Z80. And it certainly does not use any of the extended instructions introduced with the eZ80!

The custom BIOS for MP/M, like CP/M, is the layer of code that's written to support the specific hardware - things such as serial ports, disk drives, and timer interrupts. This code needs to be assembled into a SPR file type. The SPR file is a binary relocatable file used by an MP/M tool to relocate and link it with the other components of the operating system. There are two assemblers that can be used in the original tool chain: `RMAC.COM` (for Intel mnemonics) and `ZSM.COM` (for Zilog mnemonics). There are none for eZ80 extended instructions!

For me to assemble code using eZ80 instructions, I would need a way to use a modern eZ80 assembler to produce the required SPR binary relocatable file. It's a bit of a process, but it is possible. In my build, I am able to use the standard modern GNU assembler (with its eZ80 support) and run the output of that through some Digital Research tools to create the required SPR file.

An idea I have for the future is to convert the original source code for the main operating system from Intel mnemonics to Zilog mnemonics, and then perhaps tweak the code to take further advantage of the eZ80 - much like what Chris Brock did for his project.

## Things yet to be done

* At the moment, the system only supports one console (user) over serial UART0 interface.  The CRT/USB keyboard interface is not mapped.
* It only works with 4 banks - MP/M can use up to 8 banks.
* I haven't done much with it except running simple tools such as `DIR`, `PIP`, and my `HELOWLRD` program - so there may be issues.
* The MP/M internal debugging feature is not implemented - I'm not sure if I really need this.


## Whats next

* Enable the CRT/USB keyboard as a console.
* Explore more enhancements that can take advantage of the eZ80 CPU.
* Enable MP/M's maximum number of 8 banks.
* Improve and optimize the bank switching approach.
* Implement some actual concurrent and cross process communicating programs.
* Bring in the HBIOS16 emulation to allow for RomWBW distributed apps to work.
* Update MP/M to save/restore the full 24 bit register values when switching processes.

For those that have built the eZ80 for RC kit, with the linear memory and USB module, and would like to try running MP/M, you can grab a pre-release image and flash your firmware and a new USB disk image.  The release can be download from here [https://codeberg.org/dinoboards/ez80-for-rc/releases](https://codeberg.org/dinoboards/ez80-for-rc/releases)

---

```
Booting B: (CP/M 2.2)

        A:=RF0:0
        B:=USB0:0*
        C:=USB0:1
        D:=USB0:2
        E:=USB0:3

B>MPM

...

MP/M II V2.1 Loader
Copyright (C) 1981, Digital Research
Nmb of consoles     =  1
Breakpoint RST #    =  6
Memory Segment Table:
SYSTEM  DAT  FF00H  0100H
TMPD    DAT  FE00H  0100H
USERSYS STK  FD00H  0100H
XIOSJMP TBL  FC00H  0100H
RESBDOS SPR  F000H  0C00H
XDOS    SPR  CE00H  2200H
BNKXIOS SPR  C400H  0A00H
BNKBDOS SPR  A100H  2300H
BNKXDOS SPR  9F00H  0200H
TMP     SPR  9B00H  0400H
LCKLSTS DAT  9900H  0200H
CONSOLE DAT  9800H  0100H
-------------------------
MP/M II Sys  9800H  6800H  Bank 0
Memseg  Usr  0000H  C600H  Bank 1
Memseg  Usr  0000H  C600H  Bank 2
Memseg  Usr  0000H  C600H  Bank 3
        A:=RF0:0
        B:=USB0:0*
        C:=USB0:1
        D:=USB0:2
        E:=USB0:3


MP/M II V2.1
Copyright (C) 1982, Digital Research

0A>C:
0C>MPMSTAT
00:00:04 C:MPMSTAT .PRL


****** MP/M II V2.0 Status Display ******

Top of memory = FFFFH
Number of consoles = 01
Debugger breakpoint restart # = 06
Stack is swapped on BDOS calls
Memory is bank switched
BDOS disk file management is bank switched
Z80 complementary registers managed by dispatcher

Ready Process(es):
  MPMSTAT [0] Idle
Process(es) DQing:
 [CliQ    ] cli
 [ATTACH  ] ATTACH
Process(es) NQing:
Delayed Process(es):
Polling Process(es):
Process(es) Flag Waiting:
  01 -  Tick
  02 -  Clock
Flag(s) Set:
Queue(s):
  CliQ     ATTACH   MXList   MXDisk   MXProc
Process(es) Attached to Consoles:
  [0] - MPMSTAT
Process(es) Waiting for Consoles:
  [0] -  Tmp0    [0]
Process(es) Attached to Printers:
  [0] - Unattached
Process(es) Waiting for Printers:
Memory Allocation:
  Base = 9800H  Size = 6800H  Bank = 00H  Allocated to MP/M-80 [0]
  Base = 0000H  Size = C600H  Bank = 01H  * Free *
  Base = 0000H  Size = C600H  Bank = 02H  * Free *
  Base = 0000H  Size = C600H  Bank = 03H  Allocated to MPMSTAT [0]
0C>
```
