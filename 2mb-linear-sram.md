---
layout: default
title: 2MB Linear SRAM
description: Provide upto 2MB of linear addressable memory for your eZ80 CPU
tindie_product_url: https://www.tindie.com/products/dinotron/???/
github_url: https://github.com/dinoboards/???
hackaday_url: https://hackaday.io/project/196330-ez80-cpu-for-rc2014-and-other-backplanes/log/???
lectronz_product_url: https://lectronz.com/products/???
is_new: true
---

# 2MB Linear SRAM <img src="{{ site.baseurl }}/assets/new.png" style="width:36px; margin-left: 8px; position:absolute"/>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/2mb-linear-sram/pcb-profile.jpg" width="70%"/>
</div>

Let your eZ80 break the 64K barrier with this 2MB memory module.  Write applications that can address a full 2 megabytes directly, without the need for banking or paging of memory.  This memory module is designed for the ***eZ80 for RC kit***, to enable your eZ80 CPU to flex is memory muscles!

# General Description

A key feature of the eZ80 CPU is its 24bit addressing capability allowing applications to be written that can utilise up to 16MB of memory natively.  No paging or banking hardware needed.  No need for applications to be developed that limit themselves to 64K or complex paging mechanisms.

Unlike the standard Z80 memory modules that only work with a 16-bit address, the ***2MB Linear SRAM module*** is specifically designed to take full advantage of the eZ80's extended addressing size. It provides a **continuous** 2MB block of memory that can be directly accessed by the eZ80, making it possible to build or port larger applications.

# Key features

* Support up to 4 512K SRAM chips.
* Operate at lower latencies compared to 512K RAM/ROM modules.
* Compatible with existing RC2014/RCBus 16bit memory modules.
* A specifically designed port of BBC-BASIC (version 5) for development of BASIC applications*.
* A specifically designed port of Clang for building C/Assembly applications*.

> \* These languages enable the writing of application to take full advantage of the extended memory module.  The ports are still under active development.  See their respective repos for details of porting progress.

# Other technical notes

* The 2MB Linear memory module is only activated when the eZ80's Chip Select 0 (CS0) is activated.
* The modules memory address is: 0x200000 to 0x030000
* The timing of Chip Select 0 will be auto configured on boot by the eZ80's firmware, as per its detected clock.
* The timing can be viewed and changed with the **EZ80.COM** CP/M application.

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

To take full advantage of this memory module, you need applications/software written for the eZ80, that has been designed to operate within the address range of this module.

> At the moment, there is no port of CP/M to run on this memory module.  Although it is possible, and something I am working towards - at this stage to load CP/M application you still need the a standard 16bit memory.

I have developed some sample applications and tooling to take advantage of, and test, the memory module.  Boot up your system in CP/M (from the standard 16bit memory), and then load and execute special programs to bridge to the extended memory.

## Key applications available

1. ***EXE.COM***: This is a CP/M application loader, that loads an 'executable' program into the extended memory.  The Clang port is used to compile and build **.EXE** applications.
2. ***BBCeZ80.EXE***: A port of BBC BASIC (Version 5) for the eZ80 processor and the extended memory module.  Write BASIC programs that can make full use of extended memory.
3. ***EZ80.COM***: A CP/M application that allow for reporting and configuring installed memory.

For more details see:

* eZ80/Green Machine series repo: [https://github.com/dinoboards/ez80-for-rc](https://github.com/dinoboards/ez80-for-rc?tab=readme-ov-file#ez80-for-the-rcbusrc2014)
* BBC-BASIC port can be found at: [https://github.com/dinoboards/eZ80-for-rc-basic](https://github.com/dinoboards/eZ80-for-rc-basic?tab=readme-ov-file#basic-interpreter-for-the-ez80-for-rc-kit)
* Specific Clang port for the platform: [https://github.com/dinoboards/ez80-clang](https://github.com/dinoboards/ez80-clang?tab=readme-ov-file#clang-compiler-for-ez80)

## Building your own applications

It is certainly possible, if you wish, to use the Zilog ZDS II development studio, and develop your own firmware in C and Assembly and write code that uses this extended memory.  Although you may prefer to take advantage of some of the software tooling that has been developed specifically for the platform.

1. Use the port of BBC-BASIC (Version 5) that runs within this extended memory.  Write BASIC programs than can use all of the 2MB of ram directly.
2. Or, use the port of Clang for the platform - enabling the development of C/Assembly applications targeting to the extended memory.

# What's included in this kit

The full kits includes everything you need (PCB, capacitors, IC sockets, a 74HCT138 IC and one or more 512K SRAM chips).

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
* Appropriate Software to use the linear memory space.
* You still need a 16 bit memory module (such as the 512K RAM/ROM RC2014 compatible modules)*

\* Is technically possible, to develop your own firmware, to create your own bios/application systems that use this module - and thus create a bootable system that does not need a 16Bit memory module

# Resources

* Schematic: [schematic](assets/2mb-linear-sram/schematic.pdf)

{% include disclaimer.md %}
