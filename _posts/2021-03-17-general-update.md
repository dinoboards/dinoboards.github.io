---
layout: post
title: General Update
tags: msx rc2014
---


It's been a while since I posted an update to my project.  Usual boring things like work and other adult responsibilities.

I haven't had a chance to take any new pictures or videos.  So let me describe what's happened so far.

### 1.  Selling on Tindie

As you may be aware, I started selling kits online at Tindie.  This has been a fun experience - the V9958 Video board has proven to be quite popular.  I have struggled to keep the stock online.

To quote Lando Lando Calrissian:

"We're a small outpost and not very self-sufficient. I've had supply problems of every kind. I had labor difficulties..... What's so funny?"

New stock of both the Video and Game boards are online, and I didn't make any deals with the Empire!

Check out my Tindie Store, if you want to join me in the journey.

### 2. Keyboard/PPI

I've built a new iteration of the keyboard.  This design fixes flaws in the previous one - no bodging required.  Updated the design to utilise a diode for each switch, preventing key ghosting.  Without the diodes, some multi-key combinations can result in ambiguous key detection.   See the Key Ghosting section at http://map.grauw.nl/articles/keymatrix.php

### 3.  M1 Wait states

MSX typically runs at 3.5Mhz, with 1 wait state during M1 memory read cycles.  My standard RC2014 does not have such a wait state, so I added some logic into the PPI board to generate this, helping with MSX compliance/compatibility.  It can be enabled/disabled with a jumper.

### 4. Real Time Clock

Updated the RTC board - just general improved layout using the larger board size.  For the most part seems to work well and keeps time reasonably accurately.  It has a trimming capacitor to adjust the clock rate a bit, but I think I need to revisit the values of some of the clock capacitors as the adjustment seems to be too limited.

### 5. ROM/RAM Memory Board

Updated the memory board to give me 1M of onboard RAM.  And improved/fixed some of the issues with the ROM address mapping.

The Memory board allows running of original MSX BIOS ROMs or CBIOS, with MSX-DOS (Nextor).

Spent many a night working on the MSX-DOS/Nextor drivers.

### 6. Compact Flash storage system

I have spent a lot of hours working on getting the drivers for MSX-DOS/Nextor.  I wanted a diskless bootable system, so I created an embedded disk image within the ROM banks - allowing MSX-DOS to boot up without a floppy or hard-disk.

With the built in RAM disk feature, I am able to send apps/games over the serial and run from the RAM disk.

But it really needs persistent storage, so I was very pleased, that just last week, I was successful in mounting the CompactFlash card for RC2014 under MSX-DOS/Nextor.  The code for the driver was relatively simple to write, although I did stumble across the usual confusing and strange bugs.  Very pleased to be able to save/load games and apps to persistent storage.

### 7. Fully Operational Battlestar - aka MSX on RC2014.

For the most part, my RC2014 system is now a MSX computer.  I can play games, write my own code and continue my re-exploration of 80s computing.

### 8. Compatibility/Issues:

So far, I have only tested a few games and apps.  And of course, I do not have a cartridge slot to test with.  (The original ROM Cartridges for MSX are friggin expensive!)

I am using a program called SOFAROM which allows me to run ROM images from disk storage.  It loads a ROM image from disk, and dynamically patches its.  This is required as the original code is expecting to run from a Cartridge slot with a specific memory bank switching model.  You can't just simply load the code.  As such there are the inevitable compatibility issues.

Most of the MSX1 games seem to run just fine and some MSX2 game seem to work OK.  But some MSX2 games either don't load at all, or glitch.  In particular, Space Manbow, a cool horizontal scrolling game, work mostly, but glitches every now and then.  I am not sure why this might be.  Not sure if its a compatibility issue with my hardware - or that running a patched game that expects to run from the ROM cartridge slot with additional hardware, is just doomed to have issues.

Next Steps

1. Further enhance the disk drivers - some cleanup of the code and such.

2. Get kits of the Keyboard, Memory and RTC boards on Tindie.

3. Get my rc2014 Floppy module to work with the system.

4. Everything else!
