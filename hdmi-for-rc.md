---
layout: default
title: HDMI for RC
description: Generate crisp clear video output - learn and and play with a simple-to-use FPGA module.
tindie_product_url: https://www.tindie.com/products/dinotron/hdmi-for-rc/
github_url: https://github.com/dinoboards/V9958-Super
coming_lectronz_product_url: https://lectronz.com/products/
is_new: true
---

# HDMI for RC <img src="{{ site.baseurl }}/assets/new.png" style="width:36px; margin-left: 8px; position:absolute"/>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-profile.jpg" width="70%"/>
</div>

Generate crisp clear video output - learn and and play with a simple-to-use FPGA module.

# General Description

This RC2014/RCBus compatible module is based around the [Tang Nano 20K FPGA module from sipeed](https://wiki.sipeed.com/hardware/en/tang/tang-nano-20k/nano-20k.html).  Its a FGPA module
that includes a HDMI output connector.

In conjunction with the appropriate [FGPA code](https://github.com/dinoboards/V9958-Super), it will emulate a Yamaha V9958 VDP.  This emulated processor, supports all the original features of the Yamaha VDP, with some
additional extensions included to support higher resolutions and an extended palette size of 256 entries with each entry supporting full 24bit colour depth.

The module also has a 3 pin breakout for attaching an optional WS2812 LED strip.

This module is an alternative to the [MSX V99x8 Video Module](./video-v9958.md)

# Key features

* Emulate a V9958 VDP
* Support experimental higher resolutions (640x480)
* Attach and control an external WS2812 LED strip
* Digitise an analogue audio input and transmit as a digital signal to the HDMI output
* Or flash the FPGA with your own code and make it do whatever you want

# Images

<table>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-assembled2.jpg"><img src="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-assembled2.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-back.jpg"><img src="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-back.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-installed.jpg"><img src="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-installed.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-top.jpg"><img src="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-top.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td colspan="2" style="text-align: center;" ><a href="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-parts.jpg"><img src="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-parts.jpg" width="45%"/></a></td>
  </tr>
</table>


# Testing Status

The Tang Nano 20K (if you select to include it) will come flashed with an image to emulate a V9958 VDP (with extensions).  This image will also support the ability to control an optionally attached WS2812 LED strip.

The code for the Tang Nano and the associated notes can be found on its github project site [https://github.com/dinoboards/V9958-Super](https://github.com/dinoboards/V9958-Super)

The FPGA code is derived from [https://github.com/lfantoniosi/tn_vdp](https://github.com/lfantoniosi/tn_vdp).  The code has been adapted to work with the RC2014/RCBus Z80 interface; the VHDL code converted to verilog; and extensions and other changes have been applied.  As such, there is a possibility that there are now some regression to V9958 compatibility.

The HDMI/DVI output has been tested on a handful of monitor and with some passive HDMI to DVI converters.  The passive converters will typically not work if the Audio (J1) is shorted.

# What's included in this kit

The full kits includes everything you need (PCB, capacitors, resistors, IC sockets, connectors, and the ICs).  The Tang Nano 20K can be optionally included.

# Bill of Materials

|Count | Name  |
|------|-------|
| 4    |  0.1uF                     |
| 1    | 22nF     |
| 1    | 1uF     |
| 1    | 1N4148     |
| 1    | 1K Ω (3.4mm)     |
| 3    | 10K Ω (3.4mm)     |
| 1    | 2k2 Ω (3.4mm)     |
| 1    | MCP3202-BI/P     |
| 1    | 74HCT32     |
| 3    | 74LVC245     |
| 1    | Right Angle HEADER 1x3 |
| 1    | HEADER 1x2     |
| 1    | HEADER 2x3     |
| 3    | SHUNT 1x2     |
| 2    | 1x10 header socket      |
| 1    | Right Angle 40x2 Header     |
| 1    | 8 POS IC SOCKET     |
| 1    | 14 POS IC SOCKET     |
| 3    | 20 POS IC SOCKET     |
| 1    | PCB |
| 1 optional | TANG NANO 20K |


# What else do I need to make this work?

* A working RC2014/RCBus system
* An appropriate boot system - such as RomWBW with support for V9958 VDP, or other appropriate VDP software

# Port Mapping

The Tang Nano 20K is wired to the RC2014/RCBus interface such that the code within the FPGA can be configured to respond to any I/O port request.  So the ports this
module will respond to are dependant on what image is flashed onto the Tang Nano 20K.

Please see [https://github.com/dinoboards/V9958-Super](https://github.com/dinoboards/V9958-Super) for the code to emulate a V9958.  If the Tang Nano 20K is included
in the order, it will be supplied with a version from that repository already flashed.


| Port |	Description|
|------|-------------|
| $98	(r/w) | VRAM data  |
| $99 (w)	| VDP register selection |
| $99 (r)	 | Status register |
| $9A |	Palette access  |
| $9B	| Indirect register access  |
| $30 | WS2812 Pixel Current Index |
| $31 | WS2812 Pixel RGB |
| $32 | WS2812 Total Pixel Count |

* The $98 to $9B are as per a standard TMS/V9938/V9958 VDP.
* The $30 to $32 are for controlling an attached WS2812 led strip

# Jumpers/Headers

| Name | Description |
| ---- | ----------- |
| J1   | When shorted, the module will digitise any incoming analogue signal and send to the HDMI.  Please note, passive HDMI to DVI converters may not work with this enabled. |
| J2   | Program/Operate. Short the 3 jumpers when in operations.  When programming the Tang Nano, its advised to remove these jumpers |
| J3   | Transmit a clock signal to the RC2014/RCBus backplane.  Do not short this is a clock signal is already supplied to backplane |
| H1   | WS2812 connection.  Top Pin is GND, bottom pin is 5V and middle pin is the Data (D0) signal |

## Flashing Tang Nano 20K

The Tang Nano 20K is a FPGA module from [sipeed.com](https://wiki.sipeed.com/hardware/en/tang/tang-nano-20k/nano-20k.html).

To update or change the flash FPGA code, please review the instruction at: [https://github.com/dinoboards/V9958-Super/blob/main/README.md](https://github.com/dinoboards/V9958-Super/blob/main/README.md)

> You can flash the Tang Nano in-circuit, but please remove the 3 Jumpers for J2 and do **not** power to your RC2014/RCBus system.

## Programming for the V9958

Have a look at the sample apps included in this repo [apps-rc2014](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/apps-rc2014).

For specific details on programming the chip, I recommend:

* <a href="http://rs.gr8bit.ru/Documentation/V9938-programmers-guide.pdf" target="_blank">V9938 Programmers Guide</a> hosted on <a href="http://www.gr8bit.ru/gr8bit-knowledge-base.html" target="_blank">gr8bit.ru</a>
* <a href="{{ site.baseurl }}/assets/video-v9958/yamaha_v9938.pdf" target="_blank">V9938 Datasheet</a>
* <a href="{{ site.baseurl }}/assets/video-v9958/yamaha_v9958.pdf" target="_blank">V9958 Datasheet</a>
* Also worth checking out some MSX VDP specific articles at: <a href="http://map.grauw.nl/articles/" target="_blank">http://map.grauw.nl/articles/</a>.

## Activating the higher resolutions

The FPGA code emulating a V9958 VDP has some additional registers to enable the activation of a few higher resolution mode.  This feature is still a little experimental.

> If you have a `eZ80 for RC` based system, you may want to investigate the support for these resolutions available from the ez80-clang project [https://github.com/dinoboards/ez80-clang](https://github.com/dinoboards/ez80-clang)

> The BBC Basic port for the ez80 platform (see [https://github.com/dinoboards/eZ80-for-rc-basic](https://github.com/dinoboards/eZ80-for-rc-basic)) also can utilise these higher resolutions.

For description of the extended registers available, see [https://github.com/dinoboards/V9958-Super/blob/main/docs/vdp_super_res.md](https://github.com/dinoboards/V9958-Super/blob/main/docs/vdp_super_res.md)


## Programming the WS2812 Interface

There are 3 ports to control an attached WS2812 LED strip.

| Port Address | Port Name | Description |
| ------------ | --------- | ----------- |
| $30 | `WS2812_LEDIDX` | Set the LED strip's pixel read/write zero based index. Once set, send 3 bytes to the `WS2812_LEDVAL` port to set the RGB values of the pixel.
| $31 | `WS2812_LEDVAL` | Write the 3 separate RGB values for current pixel.  After assigning the index with port `WS2812_LEDIDX`, three bytes are expected to be written to this port. The three bytes represent the current pixel's Red, Green and Blue 8 bit values. After the 3 bytes are exchanged, the index is auto incremented. |
| $32 | `WS2812_LEDCNT` | Define the current maximum number of pixels available on the attached strip.  When auto indexing reaches the end (as per this setting), the index is automatically reset back to 0. |

# eZ80 Support

The ez80 clang compiler, includes C libraries to control a V9958 and the higher resolution extensions implemented by this module.  It also includes libraries to manage an attached LED strip.

The compiler can be found at: [https://github.com/dinoboards/ez80-clang](https://github.com/dinoboards/ez80-clang)

Some sample applications (for eZ80 only) can be found in the Apps section of [https://github.com/dinoboards/ez80-for-rc](https://github.com/dinoboards/ez80-for-rc)

# Resources

* Schematic: [schematic](assets/hdmi-for-rc/schematic.pdf)
* Datasheet: [Tang Nano 20K](https://wiki.sipeed.com/hardware/en/tang/tang-nano-20k/nano-20k.html#Hardware-information)

{% include disclaimer.md %}
