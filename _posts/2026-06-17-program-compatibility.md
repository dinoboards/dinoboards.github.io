---
layout: post
title: CP/M Program Compatibility on the eZ80
tags: eZ80 Green RC2014 RCBUS CPM
---

Just because we have CP/M ported to the eZ80, does not mean we can run all 'CP/M' dot COM program.

If the program is a pure CP/M program - that is - it makes no assumptions of the hardware and performs all access via the Operating System calls (BDOS), then it should be fine.

But if the program attempts to access hardware device directly, eg a sound chip, then it's unlikely to work.  This is due to the fundamental approach the eZ80 has with regards to accessing hardware devices. The differences between the standard Z80 and the eZ80 has been noted in previous posts on this site, but let's do a quick refresher.

## eZ80 and Z80 differences

There are 3 main differences between the CPUs:

1. An eZ80 has support for additional instructions (opcodes).  If a Z80 encounters these new instructions, it will just ignore them and move on.
2. A Z80 will ignore any unimplemented opcodes - but an eZ80 will reboot if it encounters an unimplemented opcode.
3. An eZ80 (due to its on-chip devices) enforces the need to address all I/O devices with a full 16 bit address range.  Most Z80 based systems typically ignore the upper 8 bits of the address range.

### Opcode differences

Some legacy CP/M programs may, perhaps inadvertently, cause the CPU to encounter unimplemented opcodes - byte sequences that do not correspond to any Z80 instruction.  When this happens on a Z80, the Z80 will just ignore the bytes and continue.  The programmer may not even realise this has happened, as perhaps, no apparent bug was produced in the program's operation. (Some cleaver programmers may even use this for specific meta programming tricks!).

If the eZ80 encounters such unimplemented opcodes, it will reboot the system.

### I/O addressing

All the Zilog CPUs technically address the 'I/O ports' of hardware devices using a 16 bit address range. But to keep things simple and cheap, many solutions were designed to ignored the upper 8 bits of this address range.  They would only use the lower 8 bits.  With this 8 bit address range, we have a maximum of 256 I/O ports - which is more than enough for most old 8 bit systems to map out a large set of hardware peripherals.

The eZ80 CPU operates the same way, that is, its I/O ports are addressed with a 16 bit address range.  But we can no longer 'ignore' the upper 8 bit address range when addressing I/O ports.  This is due to the inclusion of on-chip hardware devices (UARTS, SPI, I2C, Timers, etc) that are mapped to a reserved address range of $0000 to $00FF.

For example, on the eZ80F92 version of the eZ80, the on-chip UART device has been assigned the 16 bit address of $00C0.  So, say we have a sound chip wired to the address at $FFC0 and we run a legacy CP/M program for this sound chip.  It will attempt to communicate with the sound chip by setting the lower 8 bits of the address to $C0, leaving the value for the upper 8 bits effectively random.  As such, 3 things might happen:

1. The address generated is neither $00C0 or $FFC0 -- and **no** sound commands will be sent to the chip.
2. We might be very lucky and the upper 8 bits just happen to be $FF -- in which case it would work this one time.
3. Or we might be unlucky, and the upper 8 bits end up being $00 -- in which case we are likely to cause disruption to the UART/Serial link!


### How to fix this?

So how do we get our CP/M programs that communicate directly with hardware or have these unimplemented opcodes to work?

One option, if we have access to the source code, is to update and reassemble the program to always set the correct upper address range.

But that's no good if we don't have access the code or the time to update it.

### EMU (Emulator)

To resolve this, I wrote a special CP/M program to run other CP/M programs and resolve these compatibility issues.  It's called `EMU.COM` (Emulator).

The `EMU` program will interpret the bytes of a legacy CP/M program (much like a Z80 emulator on your PC would do).  As each byte of the program is interpreted, we can resolve all the compatiblity issues.  Thus, ensuring all I/O is mapped to the correct address and ignoring the unimplemented opcodes.

The EMU program switches back to native execution when the program makes a call to the Operating System - so all Operating System code is executed natively - with only the CP/M program's code interpreted. The same applies if the program makes a RomWBW HBIOS16 call.

Of course, the downside is the program is executed at a much slower speed.  (With an eZ80 @ 20Mhz, we achieve similar performace to a Z80 running at around 2 to 3Mhz).

At the time of writing, I have only tested this with the RomWBW distributed program `TUNE.COM`.  With the `EMU` program, I can run `TUNE.COM` targetting an AY-3-8910 based audio module directly.

The following command will run the `TUNE.COM` program under 'emulation' allowing it to talk directly to the expected hardware:


```TEXT
EMU TUNE ITERATN.PT3 --MSX
```

The EMU.COM and associated support, is included in releases from [2026-06-16](https://codeberg.org/dinoboards/ez80-for-rc/releases)
