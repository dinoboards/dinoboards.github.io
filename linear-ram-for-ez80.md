---
layout: default
title: MEGA SRAM Expansion
description: Provide up to 2MB of linear addressable memory for your eZ80 on RC
tindie_product_url: https://www.tindie.com/products/dinotron/???/
github_url: https://github.com/dinoboards/???
lectronz_product_url: https://lectronz.com/products/???
is_new: true
---

Naming elements
* 4 chip
* 512K to 2048K
* linear addressable
* static ram



# Linear SRAM for eZ80 <img src="{{ site.baseurl }}/assets/new.png" style="width:36px; margin-left: 8px; position:absolute"/>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/???/profile.jpg" width="70%"/>
</div>

This module will enable your eZ80 RCBus system to directly access more than 64K of memory at once.  No need to bank switching, as the memory is presented to the CPU's full 24bit address bus.

With the use of purpose assembled/complied application, you can run much larger programs and take full advantage of the feature of the eZ80 CPU.

# Key features

* Feature 1
* Feature 2
* Feature 3

# Images

<table>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/?????/pcb-assembled.jpg"><img src="{{ site.baseurl }}/assets/?????/pcb-assembled.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/?????/connected.jpg"><img src="{{ site.baseurl }}/assets/?????/connected.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/?????/pcb-top.jpg"><img src="{{ site.baseurl }}/assets/?????/pcb-top.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/?????/pcb-bottom.jpg"><img src="{{ site.baseurl }}/assets/?????/pcb-bottom.jpg" width="90%"/></a></td>
  </tr>
</table>


# Testing Status

There are not a low of programs that have been written to take advantage of this memory module.  At time of publishing, I have following applications under development:

1. BBCeZ80.EXE (ADL fork).  Load and execute BBC BASIC application that can address all of the available RAM.
2. eZ80.COM - A configuration and test application to configure the timings for the memory module and to enable testing performance.
3. MBROT.EXE - An ADL version of a simple Mandelbrot image generator.
4. More to come.

# Bill of Materials

|Count   | Name  |
|:------:|-------|
| 4      |  0.1uF                     |
...
| 1      | PCB |


# What else do I need to make this work?

* A working eZ80 for RC base build (eZ80 CPU, Backplane and 512k ROM/RAM Module)
* A Boot ROM image of RomWBW configured for the eZ80 platform

# Address Mapping

* The memory module is fixed to use the eZ80 CS1 chip selection
* The memory is mapped to address 0x200000 to 0x3FFFFF


# Resources

* Schematic: [schematic](assets/?????/schematic.pdf)

{% include disclaimer.md %}
