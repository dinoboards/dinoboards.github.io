---
layout: default
title: Stegosaur MSX ROM & RAM Module
description: Give your RC2014 the power of 512K ROM and 1024K RAM
product_url: https://shop.dinoboards.com.au/product/????
---

# MSX ROM & RAM Modules

A full MSX Memory System.  512K of ROM boot code and support software and up to 1MB of paged RAM.  With this module, you can boot into various MSX bios (open source CBIOS, MSX-BIOS/BASIC).

The two modules work together to map in a 512K rom image for booting, and page in the RAM using specific MSX memory mapping techniques.

The 512K ROM image is mapped across a number opf MSX "slots" and "sub-slots" - enabling the storage of BIOS, Operating System and various applications and drivers.

The 2x512K RAM is mapped, using MSX's memory page mapping, enabling compatible systems and applications the full use of the available RAM.

This module is designed for operation in conjunction with other MSX modules (CPU, GAME, RGB VIDEO, PPI & Keyboard)

# Default ROM Image

The supplied ROM image, contains the following:

* CBIOS, an open source version of MSX BIOS
* NEXTOR, an officially sanctioned open source version of MSX-DOS (based on the original code)
* MSX-DOS drivers for various hardware systems (usb, SIO/2, Compact Flash)
* Embedded ROM DISK image, enabling disk-less boot up

> Alternative ROM images (MSX-BIOS/MSX-BASIC) can be downloaded and flashed onto the supplied ROM chip (appropriate ROM programmer needed), giving your system access to MSX-BASIC and higher levels of game compatibility.  See latest releases at: <a target="_newwindow" href="https://github.com/dinoboards/yellow-msx-series-for-rc2014/releases">https://github.com/dinoboards/yellow-msx-series-for-rc2014/releases</a>

# Images

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/rom-pcb-front.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/rom-pcb-front.jpg" width="90%"/><br/>ROM PCB Front</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/rom-pcb-back.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/rom-pcb-back.jpg" width="90%"/><br/>ROM PCB Back</a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/ram-pcb-front.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/ram-pcb-front.jpg" width="90%"/><br/>RAM PCB Front</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/ram-pcb-back.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/ram-pcb-back.jpg" width="90%"/><br/>RAM PCB Back</a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/rom-assembled.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/rom-assembled.jpg" width="90%"/><br/>ROM Module Assembled</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/ram-assembled.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/ram-assembled.jpg" width="90%"/><br/>RAM Module Assembled</a></td>
  </tr>
    <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/kit-parts.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/kit-parts.jpg" width="90%"/><br/>Base Kit Parts</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/modules-connected.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/modules-connected.jpg" width="90%"/><br/>ROM-RAM inter-board connection</a></td>
  </tr>
</table>

# Memory mapping

The onboard 512K ROM is mapped according to the MSX specification, so that your system can be booted with an MSX BIOS and MSX-DOS ROM image.

The ROM is paged into the Z80's address space, allowing the banking of MSX BIOS, BIOS SUB-ROM, BIOS BOOT LOGO along with a banked MSX-DOS/NEXTOR kernel and disk drivers for RC2014 operation.

The ROM is divided into 16K banks, mapped at the following addresses and MSX slots:

| SLOT | CPU ADDRESS      | DESC                    | ROM CHIP'S ADDR    |
| ---- | ---------------- | ----------------------- | ------------------ |
| 0    | 0x0000 to 0x7FFF | MAIN ROM (48K)          | 0x00000 to 0x07FFF |
| 0    | 0x8000 to 0xBFFF | LOGO ROM (16K)          | 0x08000 to 0x0BFFF |
| 3-0  | 0x0000 to 0x3FFF | SUB ROM (16K)           | 0x0C000 to 0x0FFFF |
| 3-3  | 0x4000 to 0x7FFF | MSX-DOS/NEXTOR/ROM DISK | 0x10000 to 0x7FFFF |

The first 64K of the onboard ROM is coded to be addressed from slot 0 and 3-0.
The remaining 28 16K banks mapped to slot 3-3, using the [ASCII16](https://www.msx.org/wiki/MegaROM_Mappers#ASC16_.28ASCII.29) banking system.

The source code, build scripts and packaged releases for the alternative custom ROM images, can be found in the repo, under the [msx](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/msx#yellow-msx-for-rc2014-rom-image-builder) directory.

# Dependencies

This module must have the following MSX boards:

* Z80 Turbo CPU (or stock RC2014/RCBus Z80 CPU).
* V99x8 RGB Video Module.
* YM2149 GAME.
* PPI & Keyboard.
* 80-Way lane compatible backplane (eg: Yellow 12+1 backplane, or the Green Stegosaur 10+Slot backplane).
* Both the ROM and RAM modules must be installed together - they can not operate on their own and must have their 3 pin headers connected.

# Bill of Materials

| Count | Name                     |
| :---: | ------------------------ |
|  13   | 0.1uF                    |
|   1   | 1x3 Header socket        |
|   1   | 1x3 Header plug (17mm)   |
|   1   | ATF22V10C (RAM SELECTOR) |
|   1   | ATF22V10C (ROM-MAPPER)   |
|   1   | AS6C4008                 |
|   1   | SST39SF040               |
|   2   | 74HCT30                  |
|   1   | 74HC138                  |
|   1   | 74HCT153                 |
|   1   | 74HCT273                 |
|   1   | 74HC540                  |
|   2   | 74HCT670                 |
|   2   | Right Angle 2x20 Header  |
|   2   | 14 POS IC SOCKET         |
|   4   | 16 POS IC SOCKET         |
|   2   | 20 POS IC SOCKET         |
|   2   | 24 POS IC SOCKET         |
|   3   | 32 POS IC SOCKET         |
|   1   | PCB                      |

# Operating

When you boot up your system, you can try a few commands from the diskless embedded floppy image:

If you have used MS-DOS or CP/M you may find that MSX-DOS feel quite familiar. MSX-DOS has a degree of compatibility with standard CP/M.  Many CP/M programs will work just fine.

But MSX-DOS extends CP/M to provide support for subdirectories, and other features found in early MS-DOS.

Some things to try out and get a feel for your MSX on RC2014 system.

<table>
  <thead>
    <tr>
      <th style="white-space: nowrap;">Command</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="white-space: nowrap;"><code>DIR</code></td>
      <td>Shows list of directories/files in current drive/directory</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"><code>MEMTEST</code></td>
      <td>Will conduct a test of the RAM installed</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"><code>TYPE AUTOEXEC.BAT</code></td>
      <td>Show the contents of the AUTOEXEC.BAT file</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"><code>CD SYSTEM</code></td>
      <td>Change into a directory called system, here you will see lots of utilities you can run</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"><code>HELP</code></td>
      <td>Show the embedded commands available at the MSX-DOS prompt</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"><code>BASIC</code></td>
      <td>If your ROM contains BASIC, jumps to the BASIC interpreter</td>
    </tr>
    <tr>
      <td style="white-space: nowrap;"><code>XMODEM</code></td>
      <td>A very simply xmodem utility to allow you to download files over a compatible serial device (SIO/2)</td>
    </tr>
  </tbody>
</table>

> This page can not provide a full description of using MSX-DOS - that would be a whole book.  I suggest reading through:
* [starting guide here](https://github.com/dinoboards/Nextor/blob/v2.1/docs/Nextor%202.1%20Getting%20Started%20Guide.md)
* [MSX-DOS User Manual](https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/msx/docs/msxdos-command.txt)
* [Nextor's User Manual](https://github.com/dinoboards/Nextor/blob/v2.1/docs/Nextor%202.1%20User%20Manual.md)

> And if you would like a bit of history of the OS - where is started - [https://www.msx.org/wiki/The_History_of_MSX-DOS](https://www.msx.org/wiki/The_History_of_MSX-DOS)

## ROM Games

If you have not built a system with a cartridge slot, you can still play most games by using the utility `SROM`.  See the Author's page for more details https://www.louthrax.net/mgr/

The `SROM` utility will load a ROM image and patch it as required, to allow it to run directly from RAM.

For example, search the internet and find the pacman.rom image file, and then upload it to your CF image or the RAMDISK.

Once you have done that, to play the game, simply run this at the MSX-DOS prompt:

```
SROM PACMAN.ROM
```

# Schematic

* <a  target="_newwindow" href="./ram-schematic.pdf">RAM Schematic</a>
* <a  target="_newwindow" href="./rom-schematic.pdf">ROM Schematic</a>

# Key difference with Yellow MSX Memory

| Description     | Yellow MSX Version              | Green Stegosaur Version              |
| --------------- | ------------------------------- | ------------------------------------ |
| PCB Height      | 8.0 cm                          | 5.5 cm                               |
| Physical Layout | Single PCB for both ROM and RAM | Two separate PCBs for ROM and RAM    |
| RAM Included    | 2x512K (1MB)                    | 512K with extra 512K sold separately |
| Colour          | Yellow                          | Green                                |

# Assembly Guide

{% include soldering-order.md %}

#### NOTE 1

Solder the 1x3 Header socket onto the RAM module and the associated male connector onto the ROM Module.  The male connector needs to be soldered on the top-side of the ROM Module.

<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/memory/images/modules-connected.jpg"><img src="{{ site.baseurl }}/stegosaur/memory/images/modules-connected.jpg" width="40%"/></a>

{% include disclaimer.md %}
