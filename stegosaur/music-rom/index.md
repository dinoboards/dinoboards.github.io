---
layout: default
title: Stegosaur MSX SLOT 3-1 FOR MSX Music Module
description: ROM Support for MSX Music Module
---

<!-- product_url: https://shop.dinoboards.com.au/product/msx-music-rom -->

<div style="display: flex; justify-content: space-between; gap: 20px;">
  <div style="flex: 0 0 100px;">
    <img src="{{ site.baseurl }}/assets/coming-soon.png" width="100px"/>
  </div>
  <div style="flex: 3;">
    <h1>Stegosaur MSX SLOT 3-1 FOR MSX Music Module</h1>
    <p>Code: DB305</p>
  </div>
</div>


Add MSX-BIOS and MSX-BASIC support functions for the MSX YM2413 Music Module

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/music-rom/images/profile.jpg"><img style="width:80%" src="{{ site.baseurl }}/stegosaur/music-rom/images/profile.jpg" alt="Assembled Profiled" width="100%"/></a>
</div>
The on-board ROM includes the MSX-MUSIC basic extensions enabling the ability to write/run basic program thru its implementation of [Music Macro Language](https://en.wikipedia.org/wiki/Music_Macro_Language) (requires the MSX-Memory board with MSX-BASIC flashed).


# Key features

* Onboard ROM, with MSX-MUSIC BASIC and BIOS extensions implemented

<div class="hh1">Images</div>

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/music-rom/images/parts.jpg"><img src="{{ site.baseurl }}/stegosaur/music-rom/images/parts.jpg" width="90%"/><br/>Kit Parts</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/music-rom/images/assembled.jpg"><img src="{{ site.baseurl }}/stegosaur/music-rom/images/assembled.jpg" width="90%"/><br/>Assembled Kit</a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/music-rom/images/pcb-front.jpg"><img src="{{ site.baseurl }}/stegosaur/music-rom/images/pcb-front.jpg" width="90%"/><br/>PCB Front</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/music-rom/images/pcb-back.jpg"><img src="{{ site.baseurl }}/stegosaur/music-rom/images/pcb-back.jpg" width="90%"/><br/>PCB Back</a></td>
  </tr>
</table>


# Bill of Materials

\* Self Source Reference are supplied as a guide only.  Please double check, in case of typo or errors in listing.


| Count | Name                          | Self Sourcing*                                            |
| :---: | ----------------------------- | --------------------------------------------------------- |
|   5   | 0.1uF Ceramic Capacitors      | Mouser: 594-K104K10X7RF53L2<br/>DigiKey: BC5137-ND        |
|   1   | 74HCT21                       |                                                           |
|   1   | 74HCT32                       |                                                           |
|   1   | 74HCT138                      |                                                           |
|   1   | 74HCT273                      |                                                           |
|   1   | SST39SF040 512K NOR Flash ROM |                                                           |
|   1   | 32 POS IC SOCKET              | Mouser: 737-ICS-632-T<br/>DigiKey: 2057-ICS-632-T-ND      |
|   1   | 20 POS IC SOCKET              | Mouser: 571-1-2199298-6<br/>DigiKey: 2057-ICS-320-T-ND    |
|   1   | 16 POS IC SOCKET              | Mouser: 571-1-2199298-4<br/>DigiKey: 2057-ICS-316-T-ND    |
|   2   | 14 POS IC SOCKET              | Mouser: 571-1-2199298-3<br/>DigiKey: 2057-ICS-314-T-ND    |
|   2   | Right Angle 2x20 Header       | Mouser: 649-68020-140HLF<br/>DigiKey: 2057-PH2RA-40-UA-ND |

# What's included?

The full kits includes everything you need (PCB, capacitors, IC sockets, connectors, and the ICs).

The SST39SF040 ROM is supplied flashed with MSX-MUSIC extensions for MSX BASIC.

# What else do I need?

This module is designed to operate within a MSX configured RC2014/RCBus bootable system only.  It is not compatible with RomWBW.

You also must have the Stegosaur MSX YM2413 Music Module.

The onboard MSX-MUSIC basic extensions, requires your main Memory board have a MSX-BIOS/MSX-BASIC version flashed.

# Operation

## Rom page selection

The onboard ROM is wired to SLOT 3-1 and is expected to be mapped to page 1 (addresses: 0x4000-0x7FFF).

On power-up and reset, the SST39SF040 ROM's first 16K bank will be mapped to this page.  To change the bank, you can write to address:

`0x7DF7 in PAGE 1`

or write to address

`0xE000 in PAGE 3.`

> If SLOT 3-1 is mapped into page 3 (0xC000-0xFFFF), only the page selection register will respond to write operations - the ROM will not be selected for read or write operations for page 3 addresses.  This enables selecting addressing of the ROM address lines, without conflicting with the SST39SF040's write program commands.

## Software

#### Running MSX-BASIC code

You can run MSX-BASIC code to test out the module, a very simply basic script is as follows:

```
10 CALL MUSIC
20 PLAY #2, "CDEFAB"
RUN
```

you can also try a couple of example scripts included in the project repo:

* [msx/sample.txt](https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/music/sample.txt)
* [msx/clowns.txt](https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/music/clowns.txt)

upload these files to your system, and then at the msx-dos prompt type:

`BASIC SAMPLE.TXT` or `BASIC CLOWNS.TXT`

# Schematics

* <a target="_newwindow" href="./schematic.pdf">Schematic</a>

# Key difference with Yellow MSX RGB

| Description     | Yellow MSX Version                     | Green Stegosaur Version                       |
| --------------- | -------------------------------------- | --------------------------------------------- |
| MSX Support     | YM2413 & MSX-MUSIC ROM on single board | Seperate modules for YM2413 and MSX-BUSIC ROM |
| ROM re-flashing | supported                              | not supported                                 |
| PCB Height      | 8.0 cm                                 | 5.5 cm                                        |
| Colour          | Yellow                                 | Green                                         |

# Assembly Guide

{% include soldering-order.md %}

#### NOTE 1

There are no specific extra assembly instructions for this module.  Its a very simple build.

{% include disclaimer.md %}

