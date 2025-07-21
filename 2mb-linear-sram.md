---
layout: default
title: 2MB Linear SRAM
description: Provide up to 2MB of linearly addressable memory for your eZ80 CPU
tindie_product_url: https://www.tindie.com/products/dinotron/2mb-linear-sram-for-ez80/
github_url: https://github.com/dinoboards/ez80-for-rc
coming_lectronz_product_url: https://lectronz.com/products/
is_new: true
---

# 2MB Linear SRAM <img src="{{ site.baseurl }}/assets/new.png" style="width:36px; margin-left: 8px; position:absolute"/>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-profile.jpg" width="70%"/>
</div>

Let your eZ80 break the 64K barrier with this 2MB memory module.  Write programs that can address a full 2 megabytes directly, without the need for banking or paging of memory.  This memory module is designed for the ***eZ80 for RC kit***, to enable your eZ80 CPU to flex its memory muscles!

# General Description

A key feature of the eZ80 CPU is its 24bit addressing capability allowing programs to be written that can utilise up to 16MB of memory natively.  No paging or banking hardware needed.  No need for applications to be developed that limit themselves to 64K or complex paging mechanisms.

Unlike standard Z80 memory modules that only work with a 16-bit address, the ***2MB Linear SRAM module*** is specifically designed to take full advantage of the eZ80's 24-bit address space. It provides a **continuous** 2MB block of memory that can be directly accessed by the eZ80, making it possible to build or port larger programs.

# Key features

* Supports up to 4 512K SRAM chips.
* Operates at lower latencies compared to 512K RAM/ROM modules.

## What is the Green Machine Series of Retro Kits

The Green Machine Series of kits are designed around the RCBus/RC2014 bus, powered by an eZ80 CPU (as apposed to the Z80 CPU), and are broadly compatible with many RC2014 and RCBus kits and CP/M and RomWBW software stacks.

For more information of the eZ80 CPU, see the [eZ80 CPU kit](/ez80-for-rc).

# Other technical notes

* The 2MB Linear memory module is only active when the eZ80's Chip Select 0 (CS0) is asserted
* The modules memory address range is: 0x200000 to 0x3FFFFF.
* The timing of Chip Select 0 is automatically configured at boot by the eZ80's firmware, based on the detected clock speed
* The timing can be viewed and changed with the **EZ80.COM** CP/M program.

# Images

<table>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-assembled.jpg"><img src="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-assembled.jpg" width="90%"/></a></td>
    <td width="50%"><div style="text-align:center"><a href="{{ site.baseurl }}/assets/2mb-linear-sram/kit-components.jpg"><img src="{{ site.baseurl }}/assets/2mb-linear-sram/kit-components.jpg" width="80%"/></a></div></td>
  </tr>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-top.jpg"><img src="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-top.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-bottom.jpg"><img src="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-bottom.jpg" width="90%"/></a></td>
  </tr>
</table>


# Software Status

There are currently a number of software projects under development to take advantage of this memory module.

* A port of **BBC-BASIC*** (version 5) for development of BASIC programs [https://github.com/dinoboards/eZ80-for-rc-basic](https://github.com/dinoboards/eZ80-for-rc-basic).
* A port of **Clang*** (with associated c runtime) for building C and Assembly language programs [https://github.com/dinoboards/ez80-clang](https://github.com/dinoboards/ez80-clang).
* **EZ80.COM** - a CP/M program to allow for managing and testing the extended memory.
* **EXE.COM** - a program for loading and executing programs in the extended memory.

> \* These languages enable the writing of application to take full advantage of the extended memory module.  The ports are still under active development.  See their respective repos for details of porting progress.

* The **EXE.COM** allow execution of CP/M programs running in the extended address space - with the CLang runtime support to marshall all the CP/M operations to the 64K page.
* The CLang port still requires the 64K paged memory module (512K ROM/RAM) module with RomWBW and CP/M installed.

> Although it may be possible to use the official Zilog ZDS II development studio to create your own 'applications' - this is not a recommended approach.

# What's included in this kit

The full kit includes everything you need: PCB, capacitors, IC sockets, a 74HCT138 IC, and one or more 512K SRAM chips.

# Bill of Materials

|Count   | Name  |
|:------:|-------|
| 5      | 0.1uF                     |
| 1      | 74HCT138                  |
| 1 to 4 | AS6C4008 SRAM             |
| 1      | 16 POS IC SOCKET          |
| 3      | 32 POS IC SOCKET          |
| 1      | Right Angle 40x2 Header   |
| 1      | PCB                       |

# What else do I need to make this work?

* eZ80 Module
* An RCBus compatible 80 way backplane
* Software to use the linear memory space.
* You still need a 16 bit memory module (such as the 512K RAM/ROM RC2014 compatible modules)*

\* It is technically possible to develop your own firmware and create your own BIOS/application systems that use this module, allowing you to create a bootable system that does not require a 16-bit memory module.

# Resources

* Schematic: [Schematic](assets/2mb-linear-sram/schematic.pdf)

{% include disclaimer.md %}
