---
layout: post
title: eZ80 natively booting into CP/M Part 2
tags: eZ80 RC2014 RCBUS CPM
---

Made some more progress with porting of CP/M to the eZ80 for RC module.  Tidied up a few things and executed a few applications.


### Current Status:

1. The system can now boot from USB Storage (flash drives) for both CP/M 2.2 and ZSDOS.
2. Configures a 512K RAM disk within the Linear Memory for use by CP/M and ZSDOS. (Drive **A:**).
3. Map CP/M's **CRT:** device to the HDMI for RC module (with limited ANSI support).
4. Imported apps **XR.COM** and **XS.COM** to send and receive files over the eZ80's uart0 via the **TTY:** device of CP/M.
5. The **XR.COM** will always send and receive over CP/M's **TTY:** console (even if CP/M is currently configured as **CON:=CRT:**).
6. Implemented a very limited number of **HBIOS 16 bit** calls - enabling some RomWBW distributed apps to just work as is.
7. Imported the RomWBW distributed app, **WDATE.COM**, to set and read the current eZ80's RTC date.
8. Imported the RomWBW distributed app, **TIMER.COM**, to view the current timer tick counts.
9. Tested the ANSI rendering to the **CRT:** device, using Word Star configured for VT100.
10. Activated BBC BASIC VDU graphic character driver (for the HDMI module) - enabling various graphics modes, and various drawing primitive commands.
11. My port of eZ80 BBC BASIC now uses this VDU driver to enable the **MODE**, **MOVE**, **DRAW**, and other BBC BASIC graphic commands to work.

[Instructions for flashing disk images](https://codeberg.org/dinoboards/ez80-for-rc/src/branch/main/operating-systems/readme.md)

The latest pre-release for direct CP/M booting at time of writing is: [Release 2026-04-12](https://codeberg.org/dinoboards/ez80-for-rc/releases/tag/2026-04-12)

### Notes:

* The ANSI support is limited and needs more attention.
* The BBC BASIC VDU stream is also a work in progress, lots done - but there is a lot more to do.
* The compatibility layer for *HBIOS 16bit* is very limited at this stage, with just a tiny number of APIs implemented.

### Outstanding Tasks:

* Complete the ANSI and VDU drivers.
* Extend the *HBIOS 16bit* compatibility layer with more APIs.
* Implement an equivalent **ASSIGN.COM** application to map CP/M mapped disk to the various detected disks/slices
* Implement USB Floppies, Keyboard, Printer and map to appropriate API and devices in CP/M.
* I would like to implement other non USB storage drives - eg Compact Flash.
* I want to be able to support other _'HBIOS'_ targetted CP/M applications - eg **VGMPLAY.COM**.
* Implement a _'NVRAM'_ like feature to configure things such as (boot disk/slice, RAM Disk config, and other startup options).
* And probably lots of other ideas will come at me!

For those with the hardware, you can give try it out and follow along with my update. Download and flash the latest firmware from: [Release 2026-04-12](https://codeberg.org/dinoboards/ez80-for-rc/releases/tag/2026-04-12)

