---
layout: default
title: V99x8 Video Module
description: V9958/38 Video Module for RC2014/MSX
tindie_product_url: https://www.tindie.com/products/dinotron/v99x8-msx-rgb-video-module-for-rc2014-v38/
github_url: https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/video/README-RGB.md
hackaday_url: https://hackaday.io/project/175574-msx-compatible-boards-for-rc2014/log/186078-v9958-video-board
product_url: https://shop.dinoboards.com.au/product/v99x8-msx-rgb-video-module-for-rc2014
product_code: DB101
---

# MSX V99x8 Video Module

<p>Code: DB101</p>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-profile.jpg" width="70%"/>
</div>

A complete kit to give your RC2014 the advanced graphic capabilities of the mid to late 80s. It based around the V9938 or V9958 Video Display Processor (VDP) which powered the MSX2/MSX2+ line of 8 bit Z80 computers.

The board can be configured to operate the V9938 or the V9958 processors.

This V9958 chip, was produced by Yamaha in the late 80s and was an update to the the V9938 chip, which was itself, a successor to TI's TMS9918.  The V9938/V9958 addressed many of the shortcomings of the original TMS9918.

The V9938 and V9958 are very similar in capability.  See the relevant datasheets below to get some details of the differences.

# Key features

* Compatible with RC2014/RomWBW.
* 128K of RAM.
* RGBs via 15-pin DSUB/VGA connector.
* Support for either the V9938 or V9958 Video Display Processor.

#### added for V3.8

* Support for either a V9958 or a V9938 Video Processor
* A LM311 Voltage Comparator for improved image stability, especially for V9938 chips.

<div class="hh1">Images</div>

<table>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-base-kit-parts.jpg"><img src="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-base-kit-parts.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-parts-packaged.jpg"><img src="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-parts-packaged.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-pcb-front.jpg"><img src="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-pcb-front.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-pcb-back.jpg"><img src="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-pcb-back.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-v9938-assembled.jpg"><img src="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-v9938-assembled.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-v9958-assembled.jpg"><img src="{{ site.baseurl }}/assets/video-v9958/rgb-v3.8-v9958-assembled.jpg" width="90%"/></a></td>
  </tr>
</table>


# Bill of Materials

#### Base Kit

| Count | Name                    |
| :---: | ----------------------- |
|   2   | 22pF                    |
|   1   | 47pF                    |
|  10   | 0.1uF                   |
|   3   | 10uF                    |
|   1   | 10uF (LOW ESR)          |
|   4   | 220uF                   |
|   3   | HEADERS 1x3             |
|   3   | SHUNT 1x2               |
|   1   | 5.6uH Inductor          |
|   1   | 1N4148 Diode            |
|   1   | 15-PIN DSUB             |
|   3   | 2N3906                  |
|   1   | 2N3904                  |
|   6   | 10k Ω (3.4mm)           |
|   3   | 12k Ω (3.4mm)           |
|   3   | 27k Ω (3.4mm)           |
|   1   | 4k7 Ω (3.4mm)           |
|   1   | 2k2 Ω (3.4mm)           |
|   7   | 1k Ω (3.4mm)            |
|   1   | 470 Ω (3.4mm)           |
|   8   | 100 Ω (3.4mm)           |
|   1   | LM311N                  |
|   1   | ATF16V8                 |
|   1   | V9958 or V9938          |
|   4   | 41464C                  |
|   1   | 21.47727MHz             |
|   1   | Right Angle 2x20 Header |
|   1   | Right Angle 1x20 Header |
|   1   | 8 POS IC SOCKET         |
|   4   | 18 POS IC SOCKET        |
|   1   | 20 POS IC SOCKET        |
|   1   | 64 POS IC SOCKET        |

#### (VDP + RAM)

| Count | Name               |
| :---: | ------------------ |
|   1   | V9938 or V9958 VDP |
|   4   | 41464C RAM         |


## Output connections

You will want to think about how you plan to connect this board to your chosen monitor.  The video signals produced by 80's hardware is not trivial to connect to modern LCD monitors.  For such monitors you will need a converter to upscale the output.  Although VGA Monitors can accept a RGB signal, they are unlikely to support the lower frequency of 15Khz produced by this module.

The RGBs module provides connection via the 15-pin DSUB/VGA connector.  This output is well suited to connect via a VGA cable to a compatible HDMI/VGA up-converter that accepts a RGBs signal over the 15pin connection, such as the *GBS-8200*, *HD-VC9900* or *<a target="_newwindow" href="https://github.com/RetroScaler/gbsc-pro">RetroScaler GBSC PRO</a>* converters.  For more information on the DSUB RGB/VGA see <a target="_newwindow" href="https://www.retrorgb.com/vgaconnector.html">RetroRGB's VGA article</a>

The <a target="_newwindow" href="https://www.retrorgb.com/upscalers.html">RetroRGB upscalers article</a> has a good description for some of the converter options.

Items such as retroTink and OSSC are very high quality converters - but also have a decent price tag.

I found the low cost arcade converters such as the GBS-8200 and HD-VC9900 converters produce ok results, but recent iterations of these products have downgraded quality quite a bit.  I am unsure if these products have a consistent quality of operation and reliability when sourced from the various market places. I personally have had some units arrive that do not work as well (or at all) as other units.


The GBS-8200 can also be easily modified to produce more customisable and higher quality output, although this is a modification I have done done or tested personally.  Again, RetroRGB has it all explained at <a target="_newwindow" href="https://www.retrorgb.com/gbs-control-installation-overview.html">GBS Control</a>

My current recommendation, other than the high end converters such as retroTink and OSSC, is the *RetroScaler GBSC PRO*  for HDMI conversion. The project is hosted on github here *<a target="_newwindow" href="https://github.com/RetroScaler/gbsc-pro">https://github.com/RetroScaler/gbsc-pro</a>* - which includes a link to their store to purchase a full unit.  This product is a little more pricy than the stock GBS-8200, but you will unlikely have any conversion issues.  I have tested with this unit, and found it produces excellent results.


# DSUB pin out

<table>
  <tr>
    <th>Pin</th><th>Signal</th>
  </tr>
  <tr><td>1</td><td>Red    </td></tr>
  <tr><td>2</td><td>Green  </td></tr>
  <tr><td>3</td><td>Blue   </td></tr>
  <tr><td>4</td><td>NC     </td></tr>
  <tr><td>5-8, 10-11</td><td>GND     </td></tr>
  <tr><td>92</td><td>Optional 5V passthrough   </td></tr>
  <tr><td>12</td><td>NC   </td></tr>
  <tr><td>13</td><td>CSync  </td></tr>
  <tr><td>14,15</td><td>NC    </td></tr>

</table>

## Upscaling Testing status

My current recommended converter is the *<a target="_newwindow" href="https://github.com/RetroScaler/gbsc-pro">RetroScaler GBSC PRO</a>* .  I have tested this unit and have found it produces excellent output to my HDMI 4:3 monitor.

<div style="text-align: center;">
  <a target="_newwindow" href="https://github.com/RetroScaler/gbsc-pro"><img src="{{ site.baseurl }}/assets/images/retroscaler-gbsc-pro.jpg" width="45%"/><br/>RetroScaler GBSC PRO - Highly Recommended*</a>
</div>

<br/>

I have also tested this kit with success, using the low cost GBS-8200 and HD-VC9900 upscalers.  These have mostly produced solid stable images for the respective VGA and HDMI output.  They seem very tolerant of CSYNC voltage signal levels.

But I can no longer recommend the use of the GBS-8200 or the HD-VC9900 upscalers.  I have found that the quality of the units can vary, depending on specific iteration and some units I have recently purchased do not convert at all.

If you do wish to try the GBS-8200, I do recommend the V4.x version and not the V5.x version.  The V5.x produces a poorer quality output.  You can identify the V4 revisions by the colour of the menu control buttons.  Black for V4 and Yellow for V5.

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/gbs8200-v4.jpg"><img src="{{ site.baseurl }}/assets/gbs8200-v4.jpg" width="80%"/><br/>GBS8200 - V4 Recommended*</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/gbs8200-v5.jpg"><img src="{{ site.baseurl }}/assets/gbs8200-v5.jpg" width="80%"/><br/>GBS8200 - V5 Not Recommended</a></td>
  </tr>
</table>

> \* Caveat with the GBS-8200 recommendation is that I have found some units fail to convert.  Its possible there is a firmware variation at play.  I suspect, but have not confirmed, that the GBS-Control modification may resolve the issue.

Other upscalers, such as the OSSC and retroTink probably work very well, but I am unable to verify and confirm.  Your milage may very.  Adapter cables may need to be constructed.

I have **not** tested the unit on a real RGB CRT monitor.

> I have been advised by some builders that they have successfully tested with a real CRT, the OSSC and retrotink devices.

# Operation

<div class="hh2">Sample Apps</div>

For a base ROMWBW build you can find compatible demo apps in the [apps-rc2014](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/apps-rc2014) directory on the github project site.  They can be run under CP/M on a RC2014 system.  The prebuilt binaries can be found in the [bin](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/bin) directory.

For a MSX-DOS system, binaries for various apps and demos can be found in the [github releases](https://github.com/dinoboards/yellow-msx-series-for-rc2014/releases)

## Jumper Settings

#### J1/J2 - V9938/V9958 Selection

Short the 2 top connections when a V9938 chip is selected, and the bottom 2 connections when a V9958 chip is connected.
Incorrect position of these may result in damage to your chip.

#### J3 BUS CLK OUT

Shorting this jumper, will transmit the clock signal generated by the VDP (3.579545Mhz) to the RC2014/RCBus's CLK1 lane.  This clock signal can then be used to drive your Z80 CPU. Do **not** short this if you have another clock generator on your platform.  For best MSX compatibility, it is recommended to use this clock signal (1/6 of the main V99x8 crystal frequency), and remove any other CLK1 generators.

#### J4 5V ENABLE

Short this connection if you wish to pass through the 5V power via the 15 PIN DSUB connector (pin 9).

#### J5 CSYNC OUT

This jumper allows for the selection of the voltage level of the CSYNC output.  (1VPP or a 5V TTL).  For original CRT and old compatible 15Khz monitors, its recommended to set this to 1VPP (short the 2 right pins).

Most upscalers are likely to tolerate a 5V TTL level signal, but supplying 5V signal to a system that expects 1VPP may cause damage to the device.  So it is only recommended to set this to the 5V TTL level when the connecting device states it accepts or needs such a signal type.


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

* <a href="http://rs.gr8bit.ru/Documentation/V9938-programmers-guide.pdf" target="_blank">V9938 Programmers Guide</a> hosted on <a href="http://www.gr8bit.ru/gr8bit-knowledge-base.html" target="_blank">gr8bit.ru</a>
* <a href="{{ site.baseurl }}/assets/video-v9958/yamaha_v9938.pdf" target="_blank">V9938 Datasheet</a>
* <a href="{{ site.baseurl }}/assets/video-v9958/yamaha_v9958.pdf" target="_blank">V9958 Datasheet</a>
* Also worth checking out some MSX VDP specific articles at: <a href="http://map.grauw.nl/articles/" target="_blank">http://map.grauw.nl/articles/</a>.

# Schematic

* Schematic (revision 3.8): [schematic-video-rgb-v3.8.pdf](assets/video-v9958/schematic-video-rgb-v3.8.pdf "Schematic (revision 3.8")

# Assembly Guide

{% include soldering-order.md %}

#### NOTE 1
> Please note that due to the finer pitch pins of the V9958, the soldering of this board requires a little more finesse than the typical RC2014 through-hole based boards.  If you have built a few boards already, then you should be fine.  It's recommended that a finer pitch soldering tip be used as it can be easy to accidentally bridge some of the pins.

#### NOTE 2
> Extra care needed when inserting the V9958 into its socket - there are lots of pins, take your time to avoid bending pins.

#### NOTE 3
> **Extremely important to ensure the jumpers are in the correction position for your chosen Video Display Processor.  Incorrect selection may result in damage to your video processor.  See the silkscreen for the 2 relevant jumpers.  V3.8 and V3.9 have the top pins for the V9938 configuration and the bottom pins for V9958**


{% include disclaimer.md %}
