---
layout: default
title: USB for HDMI
description: Let your Z80 talk directly to enumerate and operate many different types of USB devices
tindie_product_url: https://www.tindie.com/products/dinotron/hdmi-for-rc/
github_url: https://github.com/dinoboards/ez80-for-rc
hackaday_url: https://hackaday.io/project/196330-ez80-cpu-for-rc2014-and-other-backplanes/log/237947-belated-progress-report
lectronz_product_url: https://lectronz.com/products/hdmi-for-rc
is_new: true
---

# HDMI for RC <img src="{{ site.baseurl }}/assets/new.png" style="width:36px; margin-left: 8px; position:absolute"/>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/hdmi-for-rc/hdmi-profile.jpg" width="70%"/>
</div>

Generate crisp clear video output - learn and and play with a simple-to-use FPGA module

* Emulates a V9958 VDP
* Support for experimental higher resolutions
* Future enhancement to control external WS2812 led strips

# General Description


# Key features


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
</table>


# Testing Status


# What's included in this kit

The full kits includes everything you need (PCB, capacitors, IC sockets, CH376S module, connectors, and the ICs).  And an optional small Flash drive that's been tested and confirmed to work.

# Bill of Materials

|Count   | Name  |
|------|-------|
| ?      |  0.1uF                     |
| 1      | PCB |


# What else do I need to make this work?

* A working RC2014/RCBus system
* An updated RomWBW ROM image configured to enable the CH376 'native' driver.

# Port Mapping

#### The board use the following IO addresses

| Port |	Description|
|------|-------------|
| $98	(r/w) | VRAM data  |
| $99 (w)	| VDP register selection |
| $99 (r)	 | Status register |
| $9A |	Palette access  |
| $9B	| Indirect register access  |

## Tang Nano 20K

The Tang Nano 20K is a FPGA module from [sipeed.com](https://wiki.sipeed.com/hardware/en/tang/tang-nano-20k/nano-20k.html).

## Programming for the V9958

Have a look at the sample apps included in this repo [apps-rc2014](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/apps-rc2014).

For specific details on programming the chip, I recommend:

* <a href="http://rs.gr8bit.ru/Documentation/V9938-programmers-guide.pdf" target="_blank">V9938 Programmers Guide</a> hosted on <a href="http://www.gr8bit.ru/gr8bit-knowledge-base.html" target="_blank">gr8bit.ru</a>
* <a href="{{ site.baseurl }}/assets/video-v9958/yamaha_v9938.pdf" target="_blank">V9938 Datasheet</a>
* <a href="{{ site.baseurl }}/assets/video-v9958/yamaha_v9958.pdf" target="_blank">V9958 Datasheet</a>
* Also worth checking out some MSX VDP specific articles at: <a href="http://map.grauw.nl/articles/" target="_blank">http://map.grauw.nl/articles/</a>.

# Resources

* Schematic: [schematic](assets/hdmi-for-rc/schematic.pdf)
* Datasheet: [Tang Nano 20K](assets/???.pdf)

{% include disclaimer.md %}
