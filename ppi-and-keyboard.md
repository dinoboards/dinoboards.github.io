---
layout: default
title: PPI & Full Size Matrix Keyboard
description: A full size keyboard kit for your RC2014 system, for use with 5 pin Cherry compatible switches.
tindie_product_url: https://www.tindie.com/products/dinotron/msx-keyboard-designed-for-rc2014/
github_url: https://github.com/dinoboards/yellow-msx-series-for-rc2014?tab=readme-ov-file#ppi-module--keyboard
hackaday_url: https://hackaday.io/project/175574-msx-compatible-boards-for-rc2014/log/185774-msx-keyboard
product_url: https://shop.dinoboards.com.au/product/msx-keyboard-designed-for-rc2014
---

# PPI & Full Size Matrix Keyboard

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/ppi-and-keyboard/installed-profile.jpg" width="60%" />
</div>

A full size keyboard kit for your RC2014 system, for use with 5 pin Cherry compatible switches, giving your kit that perfect clicky keyboard.

With diodes associated with every switch, it possible to identify all multi key press combinations - no ghost keys.


# Key Features

* Unambiguous key detection (diodes associated with every switch)
* Power, caps-lock, and code indicator LEDs
* Designed for cherry compatible 5 pin switches
* PPI Module designed around the Renesas 82C55 chip, a modern CMOS version of the original Intel 8255 Programmable Peripheral Interface chip.
* Provides the MSX slot selector lines for the ROM/RAM board.
* Optional MSX M1 Wait state generator.

# Bill of Materials

|Count   | Name                    |  Designator |
|:------:|-------------------------|-------------|
| 5      | 0.1uF                   | PPI-C1,C3,C4,C2,C5 |
| 1      | 1N4148                  | PPI-D1 |
| 1      | EXT-BUS                 | PPI-J1 |
| 1      | M1-WAIT                 | PPI-J2 |
| 1      | MSX-KYB                 | PPI-P1 |
| 1      | 82C55                   | PPI-U1 |
| 1      | 74HC138                 | PPI-U2 |
| 1      | 74HC00                  | PPI-U3 |
| 1      | 74HC153                 | PPI-U4 |
| 1      | 74HC74                  | PPI-U5 |
| 1      | Right Angle 20x2 Header | PPI |
| 1      | Right Angle header 1x20 | PPI |
| 2      | 14 POS IC SOCKET | PPI |
| 2      | 16 POS IC SOCKET | PPI |
| 1      | 40 POS IC SOCKET | PPI |
| 1      | PCB              |PPI|
| 2	     | 0.1uF               | KEYBOARD-C1,C2  |
| 81     | 1N4148	             | KEYBOARD-D1-D81 |
| 3      | 3mm LEDS            |KEYBOARD|
| 1      | IDC Socket          | KEYBOARD-P1 |
| 3      | 470 Ω               | KEYBOARD-R2,R3,R1 |
| 1      | 10k Ω x 8           | KEYBOARD-R4 |
| 73     | switches            | SW1-SW73 |
| 2      | 74HC138             | KEYBOARD-U2,U1 |
| 4	     | 2U key stabliser    |KEYBOARD|
| 1      | 6.25U key stabliser |KEYBOARD|
| 1	     | keycaps set         |KEYBOARD|
| 1	     | PCB |KEYBOARD|


# Using the keyboard on RomWBW

Although this kit is designed to work under MSX's software, it can be used in a stock RC2014 system with a correctly configured RomWBW ROM image.

See RomWBW for details on configuring and building a version of RomWBW for keyboard function.

# What's included

This project includes both the keyboard kit and the PPI interface board kit.

* Keyboard PCB and components (passive components, IDC socket, and ICs)
* PPI PCB and components (passive components, IDC socket, and ICs including the 82C55 chip)

> Please note, this kit does not include switches and keycaps.  You can choose to source these yourself, or purchase the [Keyboard caps here](https://www.tindie.com/products/dinotron/keycap-set-for-msx-rc2014-keyboard/) and [compatible switches here](https://www.tindie.com/products/dinotron/switches-and-stabilizers-for-msx-rc2014-keyboard/)

### Rainbow Cable types

Its important that the correct rainbow 16 IDC cable is used.  It needs to be a 'straight thru' type - as per image below.

<div style="text-align: center;">
  <a href="{{ site.baseurl }}/assets/ppi-and-keyboard/rainbow-cable.jpg" target="_newwindow">
    <img src="{{ site.baseurl }}/assets/ppi-and-keyboard/rainbow-cable.jpg" alt="Closeup of rainbow 16pin IDC cable" width="40%"/>
  </a>
</div>
> If the cable you received does not match this image - please contact me for a replacement.

<br/>

# What else do I need to make this work?

* You need a working RC2014 system (CPU, RomWBW, Clock, etc).
* RC2014 Enhanced Bus backplane required or the *12+1 Backplane*
* Switches, keycaps and PCB mounted stabilizers sold separately.

## Assembly Notes

My personal recommendation is solder all the passive components first, then the sockets and IDC connector.

You will certainly want to solder the diodes on the keyboard before doing the switches.

Mount the switches last -- you should get a satisfying click as you push the switch into the board - but be careful that both pins have come thru cleanly.  The pins are fairly thin and easy for them not to align and to be bent.

Start with just one or two switches first -- push in, then check pins, then solder.  Move onto a next set of switches.  Once you are more comfortable, go for bigger batches - just keep on eye on the pins.

Once all the soldering is done, you can move onto mounting the stabilizers.

## Assembling the stabilizers

To assemble the stabilizers, you can use the following images to get an idea of how they go together.

#### Line up the housing and insert as shown.  Note the orientation of the items.

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_072202703.jpg" alt="Stabilizer housing and insert" width="70%"/>
</div>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_072220367.jpg" alt="Stabilizer housing and insert" width="70%"/>
</div>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_072303033.jpg" alt="Stabilizer housing and insert" width="70%"/>
</div>

<br/>
#### Next, insert the bar as shown:

<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_072433066.jpg" alt="Stabilizer housing and insert fully assembled" width="70%" />

<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_072535751.jpg" alt="Stabilizer housing and insert fully assembled" width="70%" />
</div>

<br/>
#### And finally, carefully clip the bar into the mounting as shown:

<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_072022234.jpg" alt="Stabilizer with bar inserted" width="70%" />
</div>

<br/>

The insert should be able to move up and down as the bar is rotated.

Repeat for the other side of the bar and for the rest of the stabilizers.

Once the stabilizers are assembled, you can now mount them on the PCB as shown below.  The insert should be able to be moved up and down freely.

<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_072950829.jpg" alt="Assembled" width="70%" />
<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_073002973.jpg" alt="Assembled" width="70%" />
</div>

<br/>
#### The following images show the space bar and other stabilizers mounted onto the PCB

<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_073101732.jpg" alt="Assembled" width="70%"/>
<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210520_073036508.jpg" alt="Assembled" width="70%"/>
</div>
<br/>

<br/>

## Fully Assembled

<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/PXL_20210531_095140870.jpg" alt="Assembled"/>

(with V1.6 of PPI)

## PCB
<img src="{{ site.baseurl }}/assets/ppi-and-keyboard/image2.jpg" alt="Assembled"/>

(with V1.4 of PPI)


# Schematics

* [PPI schematic](./assets/ppi-and-keyboard/schematic-ppi.pdf "PPI Schematic")
* [Keyboard schematic](./assets/ppi-and-keyboard/schematic-keyboard.png "Keyboard Schematic")

{% include disclaimer.md %}
