---
layout: default
title: Stegosaur MSX Dual Cart Extension
description: A extension module for the 12+1 backplane to support MSX Cartridges
tindie_product_url:
github_url:
hackaday_url:
product_url:
---


<div style="display: flex; justify-content: space-between; gap: 20px;">
  <div style="flex: 3;">
    <h1>Stegosaur MSX Dual Cart Extension</h1>
    <p>Slot Extension Code: DBxxx<br/>
    Blank 16k/32k Code: DBxxx</p>
  </div>
</div>

An extension module for the 12+1 Stegosaur backplane to support MSX Cartridges

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/cart-extension/images/profile.jpg"><img style="width:50%" src="{{ site.baseurl }}/stegosaur/cart-extension/images/profile.jpg" alt="Assembled kit"/></a>
</div>


Tired of slow load times for your games?  Miss the days of flicking the power button and having your game instantly running?  Well perhaps this kit is for you.  Pair the Slot Extension with a MSX configured build, and you can load cartridge based games and software with the simple of a flick of the power button.

This module attaches to the right most slot of the 12+1 backplane and gives your system two 50pin MSX card connectors slots.  It include required decoding logic for addressing the slots as per the MSX standard.

It includes optional support for an on-board DC converter to step up the 5V from the backplane to +12/-12 voltages.

Once installed and operating on a MSX configured system, you can boot up original 1980's MSX cartridges or install new modern release cartridges from places such as https://www.msxcartridgeshop.com/

Or perhaps you can select the optional MSX Cartridge 16K/32K ROM board and flash your own (or downloaded) game and enjoy the era of instant gaming.

### Demonstration of the near identical Yellow MSX version

<iframe width="560" height="315" src="https://www.youtube.com/embed/JcZXhmn0-9o?si=o-IM3Khu5E000bcN" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


# Key features

* 2 MSX 50pin compatible cartridge slots
* Indicator LEDs when a cartridge is inserted and powered.
* Optional DC converter to supply +12/-12V*

<div class="hh1">Images</div>

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/cart-extension/images/pcb-front.jpg"><img src="{{ site.baseurl }}/stegosaur/cart-extension/images/pcb-front.jpg" width="90%"/><br/>PCB Front</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/cart-extension/images/pcb-back.jpg"><img src="{{ site.baseurl }}/stegosaur/cart-extension/images/pcb-back.jpg" width="90%"/><br/>PCB Back</a></td>
  </tr>

  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/cart-extension/images/cart-assembled.jpg"><img src="{{ site.baseurl }}/stegosaur/cart-extension/images/cart-assembled.jpg" width="90%"/><br/>Assembled Top View</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/cart-extension/images/underside-assembled.jpg"><img src="{{ site.baseurl }}/stegosaur/cart-extension/images/underside-assembled.jpg" width="90%"/><br/>Assembled Underside View</a></td>
  </tr>

  <tr>
    <td colspan=2 width="25%" style="text-align: center;"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/cart-extension/images/parts-1-1.jpg"><img src="{{ site.baseurl }}/stegosaur/cart-extension/images/parts-1-1.jpg" width="35%"/><br/>Parts</a></td>
  </tr>
</table>

# Bill of Materials

| Count | Name                       | Self Sourcing*                                     |
|:-----:|----------------------------|----------------------------------------------------|
|   3   | 0.1uF ceramic capacitors   | Mouser: 594-K104K10X7RF53L2<br/>DigiKey: BC5137-ND |
|   1   | ATF16V8                    |                                                    |
|   2   | 3mm LEDS                   |                                                    |
|   2   | 470 Ω resistors (3.4mm)    |                                                    |
|   2   | 50 Pin Card Edge Connector |                                                    |
|   1   | 4 Way Screw Terminal       |                                                    |

## On-board DC-Converter*

| Count | Name            | Self Sourcing*                    |
|:-----:|-----------------|-----------------------------------|
|   2   | 1uF Capacitor   |                                   |
|   1   | 4.7uF Capacitor |                                   |
|   1   | DC-Converter    | MEAN WELL DPU01L-12 or equivalent |


\* Most cartridges do not need or use the 12V lines.  A 4 way screw power terminal is provided if you wish supply the +12V/-12V from an external source.


# What's included?

The full kits includes everything you need (PCB, passive components, connectors, and the ICs).

The optional +/-12VDC converter, as with all parts, may be supplied with an alternative of similar specifications.

Please note that mounting stand-offs are not supplied.

# What else do I need?

The MSX Cartridge slot extension is designed to work in a build with the Stegosaur MSX Modules.  Your system needs to be able to boot as a MSX system.

You need at a minimum:

1. Stegosaur 12+1 Backplane
2. Stegosaur MSX Series Memory Module
3. Stegosaur MSX Series Video Module
4. Stegosaur MSX Series Game Module
5. Stegosaur MSX Series Keyboard/PPI Module
6. Stegosaur Turbo CPU Module (or compatible Z80 CPU module)

# Testing status

I have tested this slot extension with a limited set of MSX Cartridges.  It has been successfully tested with 3 different MSX1 original cartridges from the 80s, the recent 2021 release of *Mutants from the Deep* from https://www.msxcartridgeshop.com/ and the MegaFlashROM SD Flash unit.

It also has been successfully tested with the optional 16K/32K ROM Cartridge module.

# Operation

## MegaFlashROM

Operating this cartridge is possible, but it requires the NEXTOR kernel and disk images to be updated.

The version of NEXTOR currently supplied in the MegaFlashROM, is version 2.1.0.  The version built for the Yellow MSX Memory module, is 2.1.1 (beta).

Although NEXTOR can operator with 2 kernel systems active, there seems to be a compatibility issue with these 2 versions.

The process below, details how to update the kernel and disk images in the MegaFlashROM to a compatible new version.

> Please note, MegaFlashROM requires the a version MSX-BASIC/BIOS.  It is not compatible with CBIOS, the version of the ROM supplied with the MSX Module.  See the file [https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/msx/README.md](https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/msx/README.md) for details on updating your main ROM image.

> At this stage, you also need the Compact Flash module working in your MSX platform, to store the new MegaFlashROM images - These files are currently too large for the RamDisk.  (There is an item on my backlog to remove the need for the CompactFlash module)

When you first boot up your system, with the MegaFlashROM installed, NEXTOR should boot, but any attempt to access drives A: and B:, will return an error.

You will need to download into your system onto your Compact Flash drive, the following files:

* `opfxsd.com` from https://www.msxcartridgeshop.com/bin/opfxsd.zip
* `mfr.dsk` (from the releases section of this repo)
* `mfr.nextor.rom` (rename it to short file name such as `mfr.rom`) (also from the release section of this repo)

then execute the following at the MSXDOS command prompt:

```
opfxsd mfr.rom /i
opfxsd mfr.dsk /id
```

After that, if you reboot your system, you should boot into Mega Flash Rom's system - with access to all drives.

If you wish to reset your MegaFlashROM, follow the official process to restore your system.

1. Download the file https://www.msxcartridgeshop.com/bin/kernel.zip
2. Copy the KERNEL.DAT on a newly blank SD card (file must be copied without fragmentation)
3. Place SD card in your cartridge
4. reboot your system, holding the UP arrow key
5. Choose option F4 - Install SD kernel


# Schematics

* Dual Slot Extension Schematic <a target="_newwindow" href="./schematic.pdf">Schematic</a>

# Key difference with Yellow MSX Slot Cart Extension

| Description          | Yellow MSX Version  | Green Stegosaur Version                            |
|----------------------|---------------------|----------------------------------------------------|
| Colour               | Yellow              | Green                                              |
| On board LEDS        | 5mm LEDS            | 3mm LEDS                                           |
| Card Edge Connectors | PCB screw mountable | Equivalent alternative without screw mount support |
| Optional 16/32K Cart | Yellow Version      | Yellow Version (with Green coming soon)            |

# Assembly Guide

### General guidelines

#### Soldering item order

Generally, you want to solder items from lowest height to largest height.  Review the components you need to solder, and note their progressive heights.

1. Resistors
2. Ceramic capacitors
3. LEDs
4. Large components such as DC converter, capacitors and the Card Edge connectors
5. The 2 SIL headers - mounted on the underside of the PCB

### Specific Notes

#### NOTE 1 Socket Header

Solder these last, and ensure they are flush wit the PCB.  They need to be solder on the top of the PCB.

<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/cart-extension/images/closup-header.jpg"><img src="{{ site.baseurl }}/stegosaur/cart-extension/images/closup-header.jpg" width="40%"/></a>


{% include disclaimer.md %}
