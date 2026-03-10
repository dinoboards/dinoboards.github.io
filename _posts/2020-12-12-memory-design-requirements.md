---
layout: post
title:  "Memory Design/Requirements"
tags: msx rc2014
---

I have completed a first design and ordered a PCB for the memory board.  This board has had to solve a few challenges.

(In this posting, when I refer to MSX, I primarily mean the later MSX2 architecture.)

A complete RAM/ROM structure for an MSX involves quite a bit of logic.  The MSX memory requirements are, a little more complicated than the typical RC2014 RAM/ROM solutions.  Now remember, I did not have any experience/knowledge of MSX architecture before embarking on this endeavour, so the learnings I have summarised below may have some errors in them:

1. Slots (aka Primary Slots): MSX systems use the model of slots, to segment the Z80 address space.  Upto 4 slots can be configured.  Each slot can address 64K, divided into 16K banks.  Each bank can then be mapped to the corresponding Z80 address range.

The first slot is reserved for the MSX BIOS and BASIC rom.  Slots 1 and 2 are typically reserved for the expansion cartridges. Slots are controlled by an IO register at $A8.  This register is provided by the PPI 8255, that also manages the keyboard interface.

2. Expanded Slots (aka Secondary Slots):  Each of the primary slots may be expanded a further 4 times.  A slot is expandable, if writing to the memory mapped register at $FFFF within the slot, returns the 1's complement.  This memory mapped register controls which of the 4 sub slots are selected.

[(more details on slots)](https://konamiman.github.io/MSX2-Technical-Handbook/md/Chapter5b.html#7-slots-and-cartridges)

3. RAM Mappers:  Each of the slots may contain RAM - allowing each slot to provide upto 64k.  This solution has some limitations, so to further enhance the memory capability of the MSX series, a standard RAM mapper was introduced.

The mapper allow for the selection of a specific 16K bank to be mapped within the 64K address range of the slot.  The memory mapping is managed by 4 IO registers at $FC to $FF.

With upto 256 banks available to be selected, a total of 4MB of RAM can be address within the slot. Surely that's enough!

Multiple slots may implement the memory mapper, but all slots will share the same IO address range, thus bank selection will effect all memory mappers.

[(more information)](https://www.msx.org/wiki/Memory_Mapper)

4. ROM Mappers: There are many ROM Mapper strategies that were employed for MSX systems - usually within the context of an Expansion Card.  So if a game ROM or other application ROM needed to address more than 64K (or needed a better banking solution), they could implement their own mappers.  So a few solutions/standards were developed.  They typically involved writing to a write only memory mapped register.

The board I have designed, attempts to have all four of these models applied.  The logic is based around the same ROM and RAM chips used in the [512K ROM 512K RAM](https://rc2014.co.uk/modules/512k-rom-512k-ram-module/) board (and many others);  ST39SF040 for ROM and ASC6C4008 for RAM.

The RAM is mapped in much the same way as the RC2014 solutions, using 74HC670 registers.

The ROM is a little more complicated.  I wanted/needed 48K ROM space for the BIOS/BASIC slot 0.  An additional 16K for a Sub-ROM BIOS, in slot 3-0.  And the remaining ROM space available using a ROM Mapper in SLOT 3-3.

This is a lot of logic to squeeze onto the 100mm x 80mm board dimensions.  In my initial concepts, I thought I may have to have 2 separate boards - one for RAM and one for ROM.  But after many iterations, I managed to fit everything onto the one board, with some support from the PPI board. (Little of this is tested; hopefully nothing missing or just simply wrong!)

* The PPI 8255 board has a couple of chips, dedicated to processing the Primary Slot register -- with 2 slot address lines mapped to a couple of the RC2014 user pins.

* I added a ATF22V10C programmable logic gate to the memory board, to alleviate the logic load and also to give me a chance to rework things, should I discover any design flaws.

Will it work?  Well the boards should arrive in a few days, and it will probably take me a while to progress and diagnose - so hopefully I can get something at least kind of working soon.
