---
layout: default
title: MSX YM2149 Game Module
description: MSX compatible Sound and Game Controller Module
tindie_product_url: https://www.tindie.com/products/dinotron/ym2149-msx-game-board-for-rc2014/
github_url: https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/game
hackaday_url: https://hackaday.io/project/175574-msx-compatible-boards-for-rc2014/log/188456-sound-controller-board
product_url: https://shop.dinoboards.com.au/product/ym2149-msx-game-board-for-rc2014
---

# MSX YM2149 Game Module

Experience retro sounds with the YM2149 sound and controller module. This module provides MSX-compatible sound and controller support (joysticks, game pads, etc.) for your RC2014 system. It is also compatible with RomWBW sound applications.

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/game/installed.jpeg" alt="Installed" width="50%"/>
</div>

# Features

* YM2149 PSG - 3 channel audio, +1 noise channel
* 2 Controller Inputs (joystick, game-pad, and other input types) - MSX compatible
* optional additional audio output line, for connecting to optional MSX-MUSIC module

<div style="text-align: center;">
<iframe width="336" height="189" src="https://www.youtube.com/embed/dUCEZpBlxgY?si=SQ1P0Dx_X_H-1MLL" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

# Bill of Materials

|Count   | Name  |  Designator |
|:------:|-------|-------------|
| 4      |	10uF |	C10,C13,C12,C11
| 6      |	0.1uF	| C3,C8,C1,C5,C4,C2
| 2      |	33pF	| C7,C6
| 8      |	1N4148	| D8,D5,D7,D6,D4,D3,D2,D1
| 1      |	400mA Fuse |	F1
| 1      |	AUD-OUT	| H1
| 1      |	KYB-TYPE	| J1
| 1      |	BUS-MAP	| J2
| 1      |	JOYSTICK-A |	JY1
| 1      |	JOYSTICK-B |	JY2
| 1      |	ACTIVE |	LED1
| 1      |	3.5 Audio Socket	| P1
| 1      |	10k Ω Bussed x 12	| R1
| 3      |	4k7 Ω	| R10,R11,R4
| 2      |	10k Ω	| R2,R12
| 1      |	470 Ω	| R3
| 1      |	1M Ω	| R5
| 1      |	330 Ω	| R6
| 1      |	2k2 Ω	| R7
| 1      |	20k Ω	| R9
| 1      |	74HCT138 |	U1
| 1      |	YM2149	| U2
| 1      |	74HC00	| U3
| 1      |	74LS07	| U4
| 2      |	74HCT157 |	U6,U5
| 1      |	3.579545MHz |	X1
| 1      |	Right Angle 20x2 Header	| B1
| 1      |	Right Angle header 1x20	| B1
| 2      |	14 POS IC SOCKET |
| 3      |	16 POS IC SOCKET |
| 1      |	40 POS IC SOCKET |

# Operation

## CP/M Sample Apps for RomWBW

The `tune.com` cp/m distributed with RomWBW works just fine with the board.

## Port Mapping

Standard MSX port mapping.

| Port |  range	| Description
|:------:|-------|-------------|
| #A0  | (write)| Register write port
| #A1  | (write)|	Value write port
| #A2  | (read)	| Value read port

The following table describes the registers of the PSG:

| Register(s)	| Description |
|:------:|-------|
| 0-5	| Tone generator control |
| 6	| Noise generator control |
| 7	| Mixer control-I/O enable. Important note: bit 6 must be 0, and bit 7 must be 1.  |
| 8-10	| Amplitude control |
| 11-13	| Envelope generator control |
| 14-15	| I/O ports A & B |

## Jumper

J1 - MSX_KYB_TYPE

Used by MSX system to detect alternative keyboard types.  Leave this unconnected.

# Images

## Assembled
---------
<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/game/assembled.jpg" alt="Assembled" width="80%"/>
</div>

## Kit
---------
<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/game/kit.jpg" alt="Kit" width="80%"/>
</div>

## PCB topside
---------
<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/game/pcb-front.jpg" alt="PCB front" width="80%"/>
</div>

## PCB underside
---------
<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/game/pcb-back.jpg" alt="PCB back" width="80%"/>
</div>


# Schematic

* Schematic (1.1): [schematic.pdf](./assets/game/schematic1.1.pdf "Schematic")
* Schematic (1.6): [schematic.pdf](./assets/game/schematic.pdf "Schematic")


{% include disclaimer.md %}
