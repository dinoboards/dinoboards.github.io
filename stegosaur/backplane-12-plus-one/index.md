---
layout: default
title: Stegosaur 12 + 1 Backplane
description: A RCBus 80 way backplane ideal for MSX configuration
product_url: https://shop.dinoboards.com.au/product/stegosaur-12-plus-one/
---


<div style="display: flex; justify-content: space-between; gap: 20px;">
  <div style="flex: 3;">
    <h1>Stegosaur 12 + 1 Backplane</h1>
    <p>Code: DB315</p>
  </div>
</div>


A 13 slot RCBus 80 way backplane for RC2014 or RCBus Modules.  Well suited for the full compliment of Stegosaur MSX and Green Modules.

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/profile-empty.jpg"><img style="width:70%" src="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/profile-empty.jpg" alt="Assembled Kit" /></a>
</div>

The backplane is an alternative to the <a href="/backplane">Yellow MSX 12+1 Backplane</a>.

The 13th slot is offset slightly from the rest of the slots, to allow for connecting the MSX Cartridge slot extension***

# Key features

* 13 RC2014/RCBus 80 way slots
* 13th slot offset an extra 1cm for future extension of the MSX Cartridge module
* An optional on-board 5V DC converter
* Reset switch
* 2 way power terminal block for easy extension or alternative powering

<div class="hh1">Images</div>

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/pcb-front.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/pcb-front.jpg" width="90%"/><br/>PCB Front</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/pcb-back.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/pcb-back.jpg" width="90%"/><br/>PCB Back</a></td>
  </tr>


  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/assembled.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/assembled.jpg" width="90%"/><br/>PCB Assembled</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/parts.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/parts.jpg" width="90%"/><br/>Main Parts</a></td>
  </tr>

  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/profile-empty.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/profile-empty.jpg" width="90%"/><br/>Assembled</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/profile-installed.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-12-plus-one/images/profile-installed.jpg" width="90%"/><br/>Assembled with some modules</a></td>
  </tr>
</table>

# Bill of Materials

\* Self Source Reference are supplied as a guide only.  Please double check, in case of typo or errors in listing.

#### Base Kit

| Count | Name                       | Self Sourcing*                                         |
| :---: | -------------------------- | ------------------------------------------------------ |
|  26   | 40 Way SIL Socket*         |                                                        |
|  13   | 0.1uF Ceramic Capacitors   | Mouser: 594-K104K10X7RF53L2<br/>DigiKey: BC5137-ND     |
|   1   | 2.1mm Power Jack           | Mouser: 490-PJ-002B<br/>DigiKey: CP-002B-ND            |
|   1   | Tactile Switch             | Mouser: 506-FSM4JH<br/>DigiKey: CP-002B-ND             |
|   1   | SPDT Toggle Switch         | Mouser: 612-200MSP1T1B2M6QE                            |
|   1   | 2 Way Screw Terminal       | Mouser: 490-TB001-500-02BE                             |
|   1   | 470 Ω (3.4mm)              |                                                        |
|   1   | 3mm LEDs                   |                                                        |

#### Optional 5V Converter

| Count | Name                           | Self Sourcing*                                                                                                         |
| :---: | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
|   1   | Optional ~12V to 5DC Converter | Mouser: 919-R-78K5.0-2.0L<br/>DigiKey: 945-R-78K5.0-2.0L-ND<br/>~~Mouser: 946-MEZD71202A-G<br/>DigiKey: 1589-1465-ND~~ |


# What's included?

The full kits includes everything you need (PCB, capacitors, IC sockets, connectors, and the ICs).

The optional 5VDC converter, as with all parts, may be supplied with an alternative of similar specifications.

Please note that mounting stand-offs are not supplied.

# What else do I need?

This backplane requires modules.  Any compatible RC2014/RCBus module can operate on this backplane.


# Operation

### Main power supply

This backplane works much like many other RC2014/RCBus backplanes.  Provide an input voltage that is appropriate for the installed 5VDC Converter (typically 12V).  Note the polarity of the power supply connector - the inner pin of the DC Barrel Connector is positive and the outer shield is ground.

The 5V DC converter optionally supplied is rated at 5V @ 2 Amps.

# Schematic

* <a  target="_newwindow" href="./schematic.pdf">Schematic</a>

# Key difference with Yellow MSX 12+1 Backplane

| Description         | Yellow MSX Version                      | Green Stegosaur Version    |
| ------------------- | --------------------------------------- | -------------------------- |
| Colour              | Yellow                                  | Green                      |
| On board LEDS       | 12 5V rated Yellow 5mm LEDS + power led | Single 3mm power led       |

# Assembly Guide

### General guidelines

#### Soldering item order

Generally, you want to solder items from lowest height to largest height.  Review the components you need to solder, and note their progressive heights.

1. Resistors
2. Ceramic capacitors
3. LED
4. Reset Switch
5. Power Switch
7. Main SIP Headers
8. 5V DC Converter
9. DC Barrel Connector

### Specific Notes

Please note the following specific points regarding this module:


#### NOTE 1 Socket Headers

There are a lot of headers.  Pay close attention to their alignment, ensure square and flush with each other.  If using a dual colour combinations of headers, keep the colours coordinated and consistent.  Perhaps a black SIP for the left side and the coloured SIP for the right side.

#### NOTE 2 Capacitors for 5VDC converter

Capacitors C10 and C11 are typically not required. Footprint is provided if additional DC filter required/desired.

#### NOTE 3 Orientation the 5VDC converter

Pay attention to the required correct orientation of the converter.

#### NOTE 4 Bypassing the 5VDC converter

You can choose to power your backplane with a direct 5V power supply.

For bypassing, do not install the on-board converter and short the 5V Direct jumper and supply a good 5V power to the barrel or via the 2 way terminal block.  You typically needs at least 1 to 1.5 Amp.  2 Amp is recommended.

{% include disclaimer.md %}

