---
layout: default
title: Stegosaur YM2149 Game Module
description: MSX compatible Sound & Game Controller Module
product_url: https://shop.dinoboards.com.au/product/?????
---

# Stegosaur YM2149 Game Module

Experience retro sounds with the YM2149 sound and optional expansion game controller module. This module provides MSX-compatible sound and controller support (joysticks, game pads, etc.) for your RC2014/RCBus system. It is also compatible with RomWBW sound applications.

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/stegosaur/game/images/game-profile.jpg" alt="Installed" width="50%"/>
</div>

# Features

* YM2149 PSG - 3 channel audio, +1 noise channel
* Optional support for AY-3-8190 sound chip
* Optional expansion board for connecting 2 MSX game controller Inputs (joystick, game-pad, and other input types)
* Pseudo stereo output with the golden ratio mix


# Bill of Materials

| Count | Name                    |
| :---: | ----------------------- |
|   5   | 10uF                    |
|   4   | 0.1uF                   |
|   1   | 3.5 Audio Socket        |
|   1   | 10k Ω Bussed x 12       |
|   3   | 1k Ω (3.4mm)            |
|   1   | 1k6 Ω (3.4mm)           |
|   4   | 4k7 Ω (3.4mm)           |
|   2   | 20k Ω (3.4mm)           |
|   1   | 470 Ω (3.4mm)           |
|   2   | 74HCT138                |
|   1   | YM2149                  |
|   1   | 74HC00                  |
|   2   | Headers 1x3             |
|   1   | Headers 1x2             |
|   3   | Shunts                  |
|   2   | Right Angle 2x20 Header |
|   1   | 14 POS IC SOCKET        |
|   2   | 16 POS IC SOCKET        |
|   1   | 40 POS IC SOCKET        |
|   1   | PCB                     |

### Optional AY Support

| Count | Name             |
| :---: | ---------------- |
|   1   | 0.1uF            |
|   1   | 74HC74           |
|   1   | 14 POS IC SOCKET |

### Optional Controller Expansion

| Count | Name                            |
| :---: | ------------------------------- |
|   3   | 0.1uF                           |
|   1   | 400mA Fuse                      |
|   1   | 9-PIN DSUB CONNECTOR            |
|   1   | 10k Ω Bussed x 12 resistor      |
|   1   | 74LS07                          |
|   2   | 74HCT157                        |
|   1   | 14 POS IC SOCKET                |
|   2   | 16 POS IC SOCKET                |
|  16   | Jumper wires - female to female |
|   2   | HEADERS 2x8                     |
|   1   | PCB                             |


# Operation

## CP/M Sample Apps for RomWBW

The `tune.com` cp/m distributed with RomWBW works just fine with the board.

## Port Mapping

Standard MSX port mapping.

| Port  | range   | Description         |
| :---: | ------- | ------------------- |
|  #A0  | (write) | Register write port |
|  #A1  | (write) | Value write port    |
|  #A2  | (read)  | Value read port     |

The following table describes the registers of the PSG:

| Register(s) | Description                                                                     |
| :---------: | ------------------------------------------------------------------------------- |
|     0-5     | Tone generator control                                                          |
|      6      | Noise generator control                                                         |
|      7      | Mixer control-I/O enable. Important note: bit 6 must be 0, and bit 7 must be 1. |
|    8-10     | Amplitude control                                                               |
|    11-13    | Envelope generator control                                                      |
|    14-15    | I/O ports A & B                                                                 |

## Jumper

The following jumpers are used to select the clock frequency used by the audio chips (YM2149 or the optional AY-3-8910).  Both chips needs a clock frequency of 1.79Mhz (or close to it).  The clock is sourced from the RC2014/RCBus clock lanes as per J3.
The YM2149 has support for an onboard clock divider.

| CLK1 Frequency | Audio Chip Type | J1                  | J2                   | J3          |
| -------------- | --------------- | ------------------- | -------------------- | ----------- |
| 3.579545Mhz    | YM2149          | Left 2 pins shorted | lower 2 pins shorted | shorted     |
| 3.579545Mhz    | AY-3-8910       | Left 2 pins shorted | upper 2 pins shorted | not shorted |

### J1 - YM CLOCK DIV

When this jumper is shorted, the onboard clock divider of the YM2149 is enabled.  For operation with an AY-3-8910 this jumper must not be shorted.
The YM2149 clock divider will halve the clock rate received by the chip.

### J2 - BUS CLK DIV

Optionally enable the on-board clock divider (if installed).  If the 74HC74 is not installed, the lower 2 pins of J2 must be shorted.

### J3 - BUS CLK

Select the source of the clock signal used by the above jumpers that is ultimately supplied to the chip.  For typical MSX configuration, this should be CLK1 (2 left pins shorted), as supplied by the Video Module.

# Images

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/game-ym-installed.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/game-ym-installed.jpg" width="90%"/></a><br/>YM2149 Build</td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/game-ay-installed.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/game-ay-installed.jpg" width="90%"/></a><br/>AY-3-8190 Build</td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/controller-installed.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/controller-installed.jpg" width="90%"/></a><br/>Game Controller Expansion Build</td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/game-controller-installed.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/game-controller-installed.jpg" width="90%"/></a><br/>Game Controller Connected</td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/game-pcb-top.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/game-pcb-top.jpg" width="90%"/></a><br/>Main PCB Front</td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/game-pcb-back.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/game-pcb-back.jpg" width="90%"/></a><br/>Main PCB Back</td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/controller-top.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/controller-top.jpg" width="90%"/></a><br/>Controller Expansion PCB Front</td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/controller-back.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/controller-back.jpg" width="90%"/></a><br/>Controller Expansion PCB Back</td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/game-base-parts.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/game-base-parts.jpg" width="90%"/></a><br/>Main kit parts</td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/controller-parts.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/controller-parts.jpg" width="90%"/></a>Optional Controller Parts</td>
  </tr>
</table>



# Schematic

* Schematic (revision 1.1): <a  target="_newwindow" href="./schematic-1.1.pdf">Schematic (revision 1.1)</a>

# Key difference with Yellow MSX RGB module

| Description             | Yellow MSX Version                          | Green Stegosaur Version                                       |
| ----------------------- | ------------------------------------------- | ------------------------------------------------------------- |
| Clock Source            | On board crystal @ 3.579545Mhz              | External CLK1 or CLK2 of RC2014/RCBus                         |
| Audio Output            | Mono                                        | Stereo - (3 channels mixed into a stereo field)               |
| Audio Output Connection | 3.5mm socket and 2 pin header               | 3.5mm socket only                                             |
| Game Controller Inputs  | on main PCB                                 | optional expansion breakout board                             |
| PCB Height              | 8.0 cm                                      | 5.5 cm                                                        |
| Support YM2149          | Yes                                         | Yes                                                           |
| Support AY-3-8910       | No                                          | Yes                                                           |
| Backplane Requirement   | 80 Way RCBus or RC2014 via external Jumpers | Wired permanently to 80 Way RCBus 'User' lanes (37-40, 77-80) |
| Colour                  | Yellow                                      | Green                                                         |

# Assembly Guide

{% include soldering-order.md %}

#### NOTE 1 - U5 only required for AY-3-8910

> If you only intend to operate with the YM2149 sound chip, you do not need to solder a socket for IC U5 (74HC75) and its associated decoupling capacitor (0.1uF).  But you do need to ensure J2 has the bottom two pins shorted - either by installing the 3 pin header and applying a shunt, or by simply soldering a wire between the lower 2 pins.

#### NOTE 2 - Connecting of the Optional Controller Board

<div style="display:grid;grid-template-columns: 2fr 1fr;gap: 20px;">
<div>
<blockquote>The optional controller expansion board, is connected via two set of 8 connecting jumper wires.  As there is no 'key' to ensure the correct alignment of pins, between the main board and the controller board, its possible to inadvertently install the controller board incorrectly.  Please ensure the GND and VCC pins are aligned across the two boards and connections are followed sequentially on down the headers, as shown in marked up image.<br/>It is possible to inadvertently invert the order of individual connections - please double check you have jumpered all pins sequentially.</blockquote>
</div>
<div>
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/game/images/wiring-markup.jpg"><img src="{{ site.baseurl }}/stegosaur/game/images/wiring-markup.jpg" width="100%"/><br/>Click image to zoom in</a>
</div>
</div>

<br/>

#### NOTE 3 - 3.5mm socket requires a stereo plug

> If you insert a 'mono' plug into the socket, you will create a short across ground and one of the channels.  This module (unlike the yellow series), requires a stereo plug and associated amplifier.

{% include disclaimer.md %}
