---
layout: default
title: Stegosaur V9958 RGB Video Module
description: MSX compatible Video Module for RC2014/RCBus
product_url: https://shop.dinoboards.com.au/product/?????
product_code: DB301
---

# Stegosaur V9958 RGB

<p>Module Code: DB301</p>

A complete kit to give your RC2014/RCBus platform, the advanced graphic capabilities of the mid to late 80s. It based around the V9958 Video Display Processor (VDP) which powered the MSX2/MSX2+ line of 8 bit Z80 computers.

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-profile.jpg" width="90%"/>
</div>

The main PCB supports the installation of 64K of VRAM, sufficient for all screen modes of the processor.  With the use of the optional expansion board, the VRAM can be extended to the full 192K of VRAM that the V9958 is able to address.

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-with-192k-ram-profile.jpg" width="90%"/>
</div>


This V9958 chip, was produced by Yamaha in the late 80s and was an update to the the V9938 chip, which was itself, a successor to TI's TMS9918.  The V9938/V9958 addressed many of the shortcomings of the original TMS9918.

The V9938 and V9958 are very similar in capability.  See the relevant datasheets below to get some details of the differences.

# Key features

* Compatible with RC2014/RomWBW.
* Support for 64K of VRAM on main PCB, or expanded to full 192K of VRAM with optional VRAM expansion module.
* RGBs via 15-pin DSUB/VGA connector.

<div class="hh1">Images</div>

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/v9958-pcb-top.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-pcb-top.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/v9958-pcb-bottom.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-pcb-bottom.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/v9958-top-installed.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-top-installed.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/v9958-kit-contents.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-kit-contents.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-pcb-top.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-pcb-top.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-pcb-bottom.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-pcb-bottom.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-installed-top.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-installed-top.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-install-bottom.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-install-bottom.jpg" width="90%"/></a></td>
  </tr>
</table>

# Bill of Materials

\* Self Source Reference are supplied as a guide only.  Please double check, in case of typo or errors in listing.

#### Base Kit

| Count | Name                         | Self Sourcing*                                            |
| :---: | ---------------------------- | --------------------------------------------------------- |
|   2   | 22pF                         |                                                           |
|   1   | 47pF                         |                                                           |
|   8   | 0.1uF                        |                                                           |
|   3   | 10uF                         |                                                           |
|   1   | 220uF (LOW ESR)              |                                                           |
|   4   | 220uF                        |                                                           |
|   1   | Round Female Pin Header 1x40 |                                                           |
|   1   | HEADERS 1x3                  |                                                           |
|   1   | HEADERS 1x2                  |                                                           |
|   2   | SHUNT 1x2                    |                                                           |
|   1   | 5.6uH Inductor               | Mouser: 871-B78108S1562K                                  |
|   1   | 15-PIN DSUB                  | Mouser: 649-ICD15S13E4GV00LF<br/>DigiKey: 609-5180-ND     |
|   3   | 2N3906                       | Mouser: 637-2N3906                                        |
|   1   | 2N3904                       | Mouser: 637-2N3904                                        |
|   6   | 10k Ω (3.4mm)                | Mouser: 603-MFR-12FTF52-10K                               |
|   3   | 12k Ω (3.4mm)                | Mouser: 603-MFR-12FTF52-12K                               |
|   3   | 27k Ω (3.4mm)                | Mouser: 603-MFR-12FTF52-27K                               |
|   1   | 4k7 Ω (3.4mm)                |                                                           |
|   1   | 2k2 Ω (3.4mm)                | Mouser: 603-MFR-12FTF52-2K2                               |
|   7   | 1k Ω (3.4mm)                 | DigiKey: 13-MFR25SFRF52-4K7CT-ND                          |
|   1   | 470 Ω (3.4mm)                | Mouser: 603-MFR25SFTF52-470R                              |
|   7   | 100 Ω (3.4mm)                | Mouser: 603-MFR-12FTF52-100R                              |
|   1   | LM311N                       | Mouser: 926-LM311N/NOPB<br/> DigiKey: LM311NNS/NOPB-ND    |
|   1   | ATF16V8B-15PU                | Mouser: 556-AF16V8B15PU<br/>DigiKey:	ATF16V8B-15PU-ND     |
|   1   | 21.47727MHz                  | Mouser: 520-HCU2147-SX                                    |
|   2   | Right Angle 2x20 Header      | Mouser: 649-68020-140HLF<br/>DigiKey: 2057-PH2RA-40-UA-ND |
|   1   | 8 POS IC SOCKET              | Mouser: 649-DILB8P223TLF<br/>DigiKey: AE9986-ND           |
|   2   | 18 POS IC SOCKET             | Mouser: 571-1-2199298-5<br/>DigiKey: 2057-ICS-318-T-ND    |
|   1   | 20 POS IC SOCKET             | Mouser: 571-1-2199298-6<br/>DigiKey: 2057-ICS-320-T-ND    |
|   1   | 64 POS IC SOCKET             | DigiKey: 1212-1068-ND                                     |

#### (VDP + 64K VRAM)

| Count | Name               | Self Sourcing* |
| :---: | ------------------ | -------------- |
|   1   | V9938 or V9958 VDP |                |
|   2   | 41464C RAM         |                |

#### (VRAM Expansion)

| Count | Name                       | Self Sourcing*                                         |
| :---: | -------------------------- | ------------------------------------------------------ |
|   6   | 0.1uF                      |                                                        |
|   2   | 100 Ω (3.4mm)              | Mouser: 603-MFR-12FTF52-100R                           |
|   1   | Round Hole Pin Header 1x40 |                                                        |
|   6   | 41464C RAM                 |                                                        |
|  16   | 18 POS IC SOCKET           | Mouser: 571-1-2199298-5<br/>DigiKey: 2057-ICS-318-T-ND |

# Output connections

You will want to think about how you plan to connect this board to your chosen monitor.  The video signals produced by 80's hardware is not trivial to connect to modern LCD monitors.  For such monitors you will need a converter to upscale the output.  Although VGA Monitors can accept a RGB signal, they are unlikely to support the lower frequency of 15Khz produced by this module.

The RGBs module provides connection via the 15-pin DSUB/VGA connector.  This output is well suited to connect via a VGA cable to a compatible HDMI/VGA up-converter that accepts a RGBs signal over the 15pin connection, such as the GBS-8200 or HD-VC9900 converters.  For more information on the DSUB RGB/VGA see <a target="_newwindow" href="https://www.retrorgb.com/vgaconnector.html">RetroRGB's VGA article<a/>

The <a target="_newwindow" href="https://www.retrorgb.com/upscalers.html">RetroRGB upscalers article</a> has a good description for some of the converter options.

Items such as retroTink and OSSC are very high quality converters - but also have a decent price tag.

I have found the low cost arcade converters such as the GBS-8200 and HD-VC9900 converters produce excellent results.  The upscalers can be acquired through the usual ebay, amazon and other sellers at very reasonable prices.

The GBS-8200 can also be easily modified to produce more customisable and higher quality output - again RetroRGB has it all explained at <a target="_newwindow" href="https://www.retrorgb.com/gbs-control-installation-overview.html">GBS Control</a>


## DSUB pin out

<table>
  <tr>
    <th>Pin</th><th>Signal</th>
  </tr>
  <tr><td>1</td><td>Red    </td></tr>
  <tr><td>2</td><td>Green  </td></tr>
  <tr><td>3</td><td>Blue   </td></tr>
  <tr><td>4</td><td>NC     </td></tr>
  <tr><td>5-8, 10-11</td><td>GND     </td></tr>
  <tr><td>9, 12</td><td>NC   </td></tr>
  <tr><td>13</td><td>CSync  </td></tr>
  <tr><td>14,15</td><td>NC    </td></tr>

</table>

## Upscaling Testing status

As per the Yellow MSX RGB module, I have tested this kit with the low cost GBS-8200 and HD-VC9900 upscalers.  These have produced solid stable images for the respective VGA and HDMI output.  They seem very tolerant of CSYNC voltage signal levels.

My recommendation is to use GBS-8200 or the HD-VC9900 upscalers.  The quality is fine and I do most of my testing on these converters.  Just google their codes and you will find the usual retailers/marketplaces (eg: ebay/amazon/aliexpress) have plenty of purchase options.

There are 2 revisions of the GBS-8200 available (V4.x and V5.x).  The V5.x produces a poorer quality output.  Recommend the older V4 revisions.  You can identify the V4 revisions by the colour of the menu control buttons.  Black for V4 and Yellow for V5.

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/gbs8200-v4.jpg"><img src="{{ site.baseurl }}/assets/gbs8200-v4.jpg" width="90%"/>GBS8200 - V4 Recommended</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/gbs8200-v5.jpg"><img src="{{ site.baseurl }}/assets/gbs8200-v5.jpg" width="90%"/>GBS8200 - V5 Not Recommended</a></td>
  </tr>
</table>

Other upscalers, such as the OSSC and retroTink may work, but I am unable to verify and confirm.  Your milage may very.  Adapter cables would need to be constructed.

I have **not** tested the unit on a real RGB CRT monitor.

> I have been advised by some builders of the Yellow version of this kit (which has an identical RGB output stage as this module), that they have successfully tested with a real CRT, the OSSC and retrotink devices.

# Operation

<div class="hh2">Sample Apps</div>

For a base ROMWBW build you can find compatible demo apps in the [apps-rc2014](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/apps-rc2014) directory on the github project site.  They can be run under CP/M on a RC2014 system.  The prebuilt binaries can be found in the [bin](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/bin) directory.

For a MSX-DOS system, binaries for various apps and demos can be found in the [github releases](https://github.com/dinoboards/yellow-msx-series-for-rc2014/releases)

## Jumper Settings

#### J1 - CSYNC Voltage level

This jumper allows for the selection of the voltage level of the CSYNC output.  (1VPP or a 5V TTL).  For original CRT and old compatible 15Khz monitors, its recommended to set this to 1VPP (short the 2 left pins).

Most upscalers are likely to tolerate a 5V TTL level signal, but supplying 5V signal to a system that expects 1VPP may cause damage to the device.  So it is only recommended to set this to the 5V TTL level when the connecting device states it accepts or needs such a signal type.

#### J3 - BUS CLK

Shorting this jumper, will transmit the clock signal generated by the VDP (3.579545Mhz) to the RC2014/RCBus's CLK1 lane.  This clock signal can then be used to drive your Z80 CPU. Do **not** short this if you have another clock generator on your platform.  For best MSX compatibility, it is recommended to use this clock signal (1/6 of the main V99x8 crystal frequency), and remove any other CLK1 generators.

## Port Mapping

The board uses the standard IO addresses for MSX systems.

The first 2 ports are identical as per the TMS9918 chip.  The V9938/58 have additional ports to access higher functions.

| Port      | Description              |
| --------- | ------------------------ |
| $98	(r/w) | VRAM data                |
| $99 (w)   | VDP register selection   |
| $99 (r)   | Status register          |
| $9A       | Palette access           |
| $9B       | Indirect register access |

## Programming the chip

Have a look at the sample apps included in this repo [apps-rc2014](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/apps-rc2014).

For specific details on programming the chip, I recommend:

* <a href="http://rs.gr8bit.ru/Documentation/V9938-programmers-guide.pdf" target="_blank">V9938 Programmers Guide</a> hosted on <a target="_newwindow" href="http://www.gr8bit.ru/gr8bit-knowledge-base.html" target="_blank">gr8bit.ru</a>
* <a target="_newwindow" href="{{ site.baseurl }}/assets/video-v9958/yamaha_v9938.pdf" target="_blank">V9938 Datasheet</a>
* <a target="_newwindow" href="{{ site.baseurl }}/assets/video-v9958/yamaha_v9958.pdf" target="_blank">V9958 Datasheet</a>
* Also worth checking out some MSX VDP specific articles at: <a target="_newwindow" href="http://map.grauw.nl/articles/" target="_blank">http://map.grauw.nl/articles/</a>.

# Schematic

* <a  target="_newwindow" href="./schematic-1.1.pdf">Schematic (revision 1.1)</a>

# Key difference with Yellow MSX RGB

| Description                       | Yellow MSX Version                          | Green Stegosaur Version                                       |
| --------------------------------- | ------------------------------------------- | ------------------------------------------------------------- |
| Max VRAM on main board            | 128K                                        | 64K                                                           |
| VRAM Expandable?                  | No                                          | Yes (up to 192K)                                              |
| V9958 and V9958 Support           | Single PCB can support both VDP types       | Different PCB needed for each VDP type                        |
| V9958 WAIT signal supported       | Yes                                         | No                                                            |
| RGB Video output design           | unchanged                                   | unchanged*                                                    |
| Optional 5V out via RGB Connector | Yes                                         | No                                                            |
| PCB Height                        | 8.0 cm                                      | 5.5 cm                                                        |
| Backplane Requirement             | 80 Way RCBus or RC2014 via external Jumpers | Wired permanently to 80 Way RCBus 'User' lanes (37-40, 77-80) |
| Colour                            | Yellow                                      | Green                                                         |

> \* The Green Stegosaur RGB kit utilizes separate PCB designs for the V9938 and V9958 VDPs. This allows the V9958's PCB, to refine the layout and tracing of the power delivery components for the V9958's DAC; minimising, as much as possible, potential EM interference appearing on your display.

# Assembly Guide

{% include soldering-order.md %}

#### NOTE 1
> Due to the finer pitch pins of the V9958, the soldering of this board requires a little more finesse than the typical RC2014 through-hole based boards.  If you have built a few boards already, then you should be fine.  It's recommended that a finer pitch soldering tip be used as it can be easy to accidentally bridge some of the pins.

#### NOTE 2
> Extra care needed when inserting the V9958 into its socket - there are lots of pins, take your time to avoid bending pins.

#### NOTE 3
> There is a 220uF capacitor that, due to space constraints, needs to be mounted on the back of the PCB.  You can choose to solder this first and applying solder on the front of the PCB.  But my personal recommendation is to solder it last.  After all other components have been soldered, you can place the capacitor over on its side, as shown below, clipping the wires as required before inserting, and then soldering on the underside of PCB.

<div style="text-align: center;">
  <a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/cap-prep.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/cap-prep.jpg" width="20%"/></a>
  <a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/cap-ready.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/cap-ready.jpg" width="20%"/></a>
  <a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/cap-orientation.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/cap-orientation.jpg" width="28%"/></a>
  <a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/cap-soldered.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/cap-soldered.jpg" width="20%"/></a>
</div>

<br/>

#### NOTE 4

<div style="display:grid;grid-template-columns: 3fr 1fr;gap: 20px;">
<div>
<blockquote>Ensure the 1 x 3 Round Machine Header (low profile) is mounted straight and flush, to ensure a good fit for the optional memory expansion board.</blockquote>
</div>
<div>
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-header-installed.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/ram-expansion-header-installed.jpg" width="100%"/></a>
</div>
</div>

<br/>

#### NOTE 5

<div style="display:grid;grid-template-columns: 3fr 1fr;gap: 20px;">
<div>
<blockquote>Pay close attention to the position of Jumper J3 1 x 2 header, the 5.6uH inductor and 0.1uF capacitor, as they have a minimal fit between the 64pin IC socket and mounting right angler header.</blockquote>
</div>
<div>
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/header-inductor-cap-fit.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/header-inductor-cap-fit.jpg" width="100%"/></a>
</div>
</div>

#### NOTE 6 - Assembling/soldering order for the Options Expansion Module

> The bottom of the VRAM exapnsion RAM module, once soldered, will make contact with the V99x8 VDP plastic cover.  The PCB is designed to be installed at a slight angle.  To ensure a good fit perform the assembly in the following process:

1. Solder the resistors, then the 0.1uF capacitors.
2. Solder the 6 "18 PIN IC" sockets.
3. Clip the underside of the soldered pins of all components, including ICs, to allow for as much clearance when installing as possible.
4. Reflow the solder joints, after clipping, to ensure a good connection of the pins is maintained.
5. Cut 4 lengths of 18 pins, from the Round Machine male headers.
6. Cut 1 length of 3 pins, of Round Machine male headers.
7. Use the V99x8 video module as a jig, by placing the headers into the relevant sockets, with the correct orientation of the pins (see image under Note 7).
8. Place the VRAM expansion PCB over the top, noting the angle - ensure all headers pins have sufficient height through the VRAM expansion module. (If height is insufficient, review the underside of the VRAM Expansion module to ensure the pins are trimmed sufficiently)
9. Solder the Headers on the top of VRAM Expansion module.

**TODO ADD IMAGES WHEN THE 0.8mm heigh PCB arrives**

#### NOTE 7 - Expansion VRAM pin orientation

> Note the orientation of how the round headers need to be soldered to the expansion module.

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/v9958/images/vram-expansion-pins-soldered.jpg"><img src="{{ site.baseurl }}/stegosaur/v9958/images/vram-expansion-pins-soldered.jpg" width="55%"/></a>
</div>

<br/>


{% include disclaimer.md %}
