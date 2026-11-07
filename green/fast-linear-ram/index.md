---
layout: default
title: 2MB Fast Linear SRAM
description: upto 2MB of fast linear memory for the ozRaptor board
product_url: https://shop.dinoboards.com.au/product/2mb-fast-ram-for-ozraptor/
---

# 2MB Fast Linear SRAM

<p>Code: DB213</p>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/green/sram-fully-assembled-profiled.jpg" width="70%"/>
</div>

An alternative to the <a href="/2mb-linear-sram">RCBus 2MB linear memory</a> module, this module uses a specially designed interface to allow for high speed memory operation.  Break the 64K barrier with this high speed memory module designed for the <a href="/green/ozraptor">ozRaptor module</a>

The ozRaptor module supports up to two of these modules, to allow for up to 4MB of linear direct access 0 wait state memory.

# General Description

A key feature of the eZ80 CPU is its 24bit addressing capability allowing programs to be written that can utilise up to 16MB of memory natively.  No paging or banking hardware needed.  No need for applications to be developed that limit themselves to 64K or complex paging mechanisms.

Unlike standard Z80 memory modules that only works with a 16-bit address, the ***Fast 2MB Linear RAM module*** is specifically designed to take full advantage of the eZ80's 24-bit address space. It provides a **continuous** 2MB block of memory that can be directly accessed by the eZ80, making it possible to build or port larger programs.

# Key features

* Supports up to 4 512K SRAM chips.
* Operates at 0 cycle wait states to achieve maximum performance of your eZ80 system.

# Other technical notes

* The 2MB Linear memory module is only active when the eZ80's Chip Select 1 (CS1) is asserted
* The modules memory address range can be configured for operating at: 0x400000 to 0x5FFFFF or 0x600000 to 0x7FFFFF.
* The timing can be viewed and changed with the **EZ80.COM** CP/M program.

# Images

<table>
  <tr>
    <td width="50%"><div style="text-align:center"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/sram-pcb-topside.jpg"><img src="{{ site.baseurl }}/assets/green/sram-pcb-topside.jpg" width="90%"/></a></div></td>
    <td width="50%"><div style="text-align:center"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/sram-underside.jpg"><img src="{{ site.baseurl }}/assets/green/sram-underside.jpg" width="90%"/></a></div></td>
  </tr>
  <tr>
    <td width="50%"><div style="text-align:center"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/sram-by-4-soldered.jpg"><img src="{{ site.baseurl }}/assets/green/sram-by-4-soldered.jpg" width="90%"/></a></div></td>
    <td width="50%"><div style="text-align:center"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/sram-by-1-soldered-profile.jpg"><img src="{{ site.baseurl }}/assets/green/sram-by-1-soldered-profile.jpg" width="90%"/></a></div></td>
    </tr>
  <tr>
    <td width="50%"><div style="text-align:center"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/sram-by-4-topside-soldered.jpg"><img src="{{ site.baseurl }}/assets/green/sram-by-4-topside-soldered.jpg" width="90%"/></a></div></td>
    <td width="50%"><div style="text-align:center"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/fast-sram-base-kit.jpg"><img src="{{ site.baseurl }}/assets/green/fast-sram-base-kit.jpg" width="90%"/></a></div></td>
  </tr>
  <tr>
    <td width="50%"><div style="text-align:center"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/sram-caps-parts.jpg"><img src="{{ site.baseurl }}/assets/green/sram-caps-parts.jpg" width="90%"/></a></div></td>
  </tr>
</table>


# Software Status

There are currently a number of software projects under development to take advantage of this memory module.

* A port of **BBC-BASIC*** (version 5) for development of BASIC programs [https://codeberg.org/dinoboards/eZ80-for-rc-basic](https://codeberg.org/dinoboards/eZ80-for-rc-basic).
* A port of **Clang*** (with associated c runtime) for building C and Assembly language programs [https://codeberg.org/dinoboards/ez80-clang](https://codeberg.org/dinoboards/ez80-clang).
* **EZ80.COM** - a CP/M program to allow for managing and testing the extended memory.
* **EXE.COM** - a program for loading and executing programs in the extended memory.

> \* The languages enable the writing of application to take full advantage of the extended memory module.  The ports are still under active development.  See their respective repos for details of porting progress.

* The **EXE.COM** allow execution of CP/M programs running in the extended address space - with the CLang runtime support to marshall all the CP/M operations to the 64K page.
* The CLang port still requires the 64K paged memory module (512K ROM/RAM) module with RomWBW and CP/M installed.

> Although it may be possible to use the official Zilog ZDS II development studio to create your own 'applications' - this is not a recommended approach.

The **EZ80.COM** and **EXE.COM** applications can be downloaded from the one of the official releases on the github repo : [https://codeberg.org/dinoboards/ez80-for-rc/releases](https://codeberg.org/dinoboards/ez80-for-rc/releases).  Download the releases.zip under the Assets section of the release you want to use.  Within that zip file you find the compiled applications.  These are standard CP/M applications and will only execute on an eZ80 CPU.

# Testing the memory

The **EZ80.COM** CP/M application can be used to verify your memory module is working.  Once you have copied it onto your system (typically with xmodem) you can run it to scan, test and adjust the timings of the memory.

Running **EZ80.COM** with no arguments will report timings:

```text
C>EZ80
              CPU frequency: 25000000 Hz
            Z80 Environment: eZ80's Z80 Compatibility
      On-chip Flash W/S: 1  (80ns)
        Main Memory B/C: 3  (360ns)
Extended Memory CS0 W/S: 2  (120ns)
Extended Memory CS1 W/S: 0  (40ns)
                I/O B/C: 4  (480ns)
         TMR1 Tick rate: 60 (Counter: 218)
```

To get a list of command line options, run with the `-?` argument

```text
C>EZ80 -?
Usage: ez80 [options]
Options:
  -F=<number>W      Set On-chip Flash Wait States
  -M=<number>[W|B]  Set Main Memory Wait States or Bus Cycles (CS3)
  -M0=<number>[W|B] Set Extended Memory Wait States or Bus Cycles (CS0)
  -M1=<number>[W|B] Set Extended Memory Wait States or Bus Cycles (CS1)
                    Wait States: 0-7, Bus Cycles: 1-15
  -I=<number>[W|B]  Set I/O Wait States or Bus Cycles (CS2)
  -S                Scan extended memory
  -P                Measure Main Memory Performance
  -T=<number>       Set tick frequency rate (50 or 60)
  -? /?             Show this help message
```

As shown in the help above, to scan and verify your extended memory is working run with the `-S` option:

```text
C>EZ80 -S
Searching for memory installed from 0x200000 to 0x7F0000
512K bank at 0x200000: None
512K bank at 0x280000: None
512K bank at 0x300000: None
512K bank at 0x380000: None
512K bank at 0x400000: OK
512K bank at 0x480000: OK
512K bank at 0x500000: OK
512K bank at 0x580000: OK
512K bank at 0x600000: OK
512K bank at 0x680000: OK
512K bank at 0x700000: OK
512K bank at 0x780000: OK

4096kb available at 0x400000

Memory @ 0x400000: 8192.00 KB/s

```


# What's included in this kit

This kit will include all the required parts for the module (PCB, SMD capacitors, and SMD integrated circuits)

This kit can also be supplied with the SMD parts already soldered for you.

# Bill of Materials

| Quantity | Component                  | Self Sourcing*                                            |
|:--------:|----------------------------|-----------------------------------------------------------|
|    5     | 1uF (0805 imperial SMD)    | Digikey: CL21B105KOFNNNG                                  |
|    1     | 74AHCT138 (16-SOIC)        | Digikey: SN74AHCT138DR                                    |
|  1 to 4  | CY7C1049GN-10VXIT (36-SOJ) | Digikey: CY7C1049GN-10VXIT                                |
|    2     | Right Angle 2x20 Header    | Digikey: 2057-PH2RA-40-UA-ND<br/>Mouser: 649-68020-140HLF |
|    1     | PCB                        |                                                           |

# What else do I need to make this work?

* a <a href="/green/ozraptor/">ozRaptor</a> with required RCBus modules.

# Jumpers/Headers

#### J0..J3 - MEMORY ADDRESS CONFIGURATION

J0 to J3 are pads that need to be bridge to enable a specific memory address operations.  The module support 2 memory ranges.

Solder and short the top two pads of each, to configure the memory for address range 0x400000 to 0x05FFFF

And short the bottom two pads of each, to configure the memory for address range 0x060000 to 0x7FFFF

> ***WARNING: Its important not to insert two memory modules into an ozRaptor base configured for the same address range.  This will conflict and possible damage the RAM or the eZ80 CPU.***

> ***WARNING: Do not short all three pads, as this would also cause operational conflicts.***

# Resources

* Schematic: [Schematic](/green/fast-linear-ram/schematic.pdf)

# Assembly Guide

<div style="display: flex; flex-direction: row-reverse; justify-content: space-between; align-items: flex-start; gap: 20px;">

  <div style="flex: 0 0 20%;">
    <a href="{{ site.baseurl }}/assets/green/sram-chip-top.jpg" target="_newwindow"><img src="{{ site.baseurl }}/assets/green/sram-chip-top.jpg" style="width: 100%; height: auto;"/></a>
    <a href="{{ site.baseurl }}/assets/green/sram-chip-underside.jpg" target="_newwindow"><img src="{{ site.baseurl }}/assets/green/sram-chip-underside.jpg" style="width: 100%; height: auto;"/></a>
  </div>

  <div >
  <p>The module can be ordered with all SMD parts soldered.  Or if you prefer, you can solder the chips and capacitors yourself.</p>

<p>This module's components are all SMD parts (except for the right hand connector headers).</p>

<p>The SMD parts can be soldered with a conventional soldering iron.  If this will be your first attempt to solder SMD components you will need to take your time and pay attention to the points below.  (you may wish to practice on a cheap throw away board)</p>

<p>The specific parts have been chosen specifically to assist in visual hand soldering.</p>

<ol>
  <li>The decoupling capacitor are 0805 (imperial), which can be easily seen and positioned using tweezers.</li>
  <li>The SRAM chips are in a 36-SOJ Small Outline J-Lead package.  These have leads that curl under the IC.  The pitch of the pins are 1.27mm, which is half the pitch (2.54mm) of a typical through hole IC.</li>
</ol>
</div>
</div>

<hr/>

#### Soldering item order

1. Solder each SRAM chip, one at a time, verifying the connections before moving to the next SRAM chip.

2. After the SRAM chips are done, solder the 74AHCT138 decoder IC.

3. After all the ICs are done & connection continuity verified, only then proceed with soldering the capacitors.

4. And finally, solder the 3 set of headers (2x20, 2x3 and 2x16).

<hr/>

#### NOTE 1 - HAND SOLDERING COMPONENTS - TOOLS

The following tools and equipment is recommended:

<div style="display: flex; flex-direction: row-reverse; justify-content: space-between; align-items: flex-start; gap: 20px;">

  <div style="flex: 0 0 35%;">
    <a href="{{ site.baseurl }}/assets/green/tools.jpg" target="_newwindow"><img src="{{ site.baseurl }}/assets/green/tools.jpg" alt="SMD soldering tools" style="width: 100%; height: auto;"/></a>
  </div>

  <div >
    <ul>
      <li>A soldering iron with a small tip.</li>
      <li>Small diameter soldering wire - say around 0.5mm.</li>
      <li>Some tweezers for picking and moving the SMD parts.</li>
      <li>A tube of no-clean flux. Recommend syringe dispensing container.</li>
      <li>Some PCB/flux cleaning fluid such as isopropyl alcohol.</li>
      <li>Visual aid - depending on your eyesight a decent magnify lamp may be all you need.</li>
      <li>A multimeter to check continuity and potential bridging.</li>
    </ul>
  </div>
</div>


<hr/>

#### NOTE 2 - CLEAN THE PCB FIRST

Before starting, clean the PCB using a cleaner such isopropyl alcohol.

<hr/>

#### NOTE 3 - FIRST SRAM CHIP

<div style="display: flex; flex-direction: row-reverse; justify-content: space-between; align-items: flex-start; gap: 20px;">

  <div style="flex: 0 0 35%;">
    <video id="fullscreen-video" controls width="100%" preload="metadata">
      <source src="{{ site.baseurl }}/assets/green/sram-p1.mp4" type="video/mp4">
         Your browser does not support the video tag.
      </source>
    </video>
    <video id="fullscreen-video" controls width="100%" preload="metadata">
      <source src="{{ site.baseurl }}/assets/green/sram-p2.mp4" type="video/mp4">
         Your browser does not support the video tag.
      </source>
    </video>
  </div>

  <div>
    <ol>
    <li>Pre-tin one top pad of the SRAM footprint.</li>
    <li>Place the IC into position - ensuring its aligned.  While holding a small downward pressure on the chip, re-heat the pad to weld the pin.</li>
    <li>Review the chip's position - if not satisfied with it position, re-apply heat the to pin and carefully tap your IC into position.</li>
    <li>Place some flux on the opposite pin.</li>
    <li>Place a small amount of solder on the tip of the iron.</li>
    <li>And now place the tip onto the pin - solder should now flow and weld the pin.</li>
    <li>Double check your IC is aligned - and re-align if needed.</li>
    </ol>
  </div>
</div>

> On the initial 2 joint soldering, ensure the chip is pushed down against the PCB - otherwise it might 'float' a little and prevent a good soldering.

> If you get some pins bridging - for the moment, just ignore it - just focus on ensuring the IC is positioned correctly.

<hr/>

#### NOTE 4 - COMPLETE THE SOLDERING OF ALL THE PINS.

<p>There are numerous approached you can use to solder the remaining pins.</p>

<div style="display: flex; flex-direction: row-reverse; justify-content: space-between; align-items: flex-start; gap: 20px;">

  <div style="flex: 0 0 35%;">
    <video id="fullscreen-video" controls width="100%" preload="metadata">
      <source src="{{ site.baseurl }}/assets/green/sram-p3.mp4" type="video/mp4">
         Your browser does not support the video tag.
      </source>
    </video>
  </div>
  <div>
  <h4>Soldering with wire only:</h4>
  <ol>
    <li>Place the tip of the iron on the pad and pin and pre-heat the joint.
      </li>
      <li>Remove the iron.
      </li>
      <li>Place your solder wire onto the joint, and re-apply the iron.  You want the inner flux of the wire to melt into the pad to ensure a good join.
      </li>
      <li>If you feel there is insufficient solder on the joint, repeat the above steps.</li>
    </ol>
  </div>
</div>


<div style="display: flex; flex-direction: row-reverse; justify-content: space-between; align-items: flex-start; gap: 20px;">

  <div style="flex: 0 0 35%;">
    <video id="fullscreen-video" controls width="100%" preload="metadata">
      <source src="{{ site.baseurl }}/assets/green/sram-p4.mp4" type="video/mp4">
         Your browser does not support the video tag.
      </source>
    </video>
  </div>

  <div>

<h4>Soldering with flux:</h4>
<ol>
    <li>Apply some flux to the pins/pads.
    </li>
    <li>Apply a small amount of solder to the tip of your iron.
    </li>
    <li>Place the iron at the join and let the solder flow.
    </li>
    <li>Remember to clean your iron's tip at least every 2 or 3 joints.
    </li>
    <li>You may also want to clean flux and add new flux as you progress.
    </li>
</ol>
  </div>
</div>

<hr/>

#### NOTE 5 - CHECK CONTINUITY

<div style="display: flex; flex-direction: row-reverse; justify-content: space-between; align-items: flex-start; gap: 20px;">

  <div style="flex: 0 0 35%;">
    <video id="fullscreen-video" controls width="100%" preload="metadata">
      <source src="{{ site.baseurl }}/assets/green/sram-p5.mp4" type="video/mp4">
         Your browser does not support the video tag.
      </source>
    </video>
  </div>

  <div>

<p>Using your multimeter, in continuity mode, check that each pin of the IC are connected to the corresponding pad of the free RAM footprints.  Also check that each pin is not shorting with it neighbouring pin.</p>

> When placing a probe on the IC's pin - do not press hard against the pin - as this might give you a false positive if the pin is floating and is not actually soldered.

<p>Almost all pins of each IC is connected in parallel.  The only pins that are not connected are:</p>

<p>PIN 6 - this pin should connect to the center pad of J0<br/>
PIN 36 - (top right pin) is N/C<br/>
PIN 19 - (bottom right pin) is also N/C</p>

<p>All other pins should mirror to the other RAM chip's footprint.</p>

<p>If you identify any pins that are not connected - apply some flux and flow a tiny amount of additional solder.</p>
<p>If you identify any bridging - apply some flux and draw excess solder with a clean iron tip.</p>

<p>After each SRAM chip is done & verified, proceed to solder the next item.</p>
</div>
</div>

<hr/>

#### NOTE 6 - SOLDERING CAPACITORS

<div style="display: flex; flex-direction: row-reverse; justify-content: space-between; align-items: flex-start; gap: 20px;">

  <div style="flex: 0 0 35%;">
    <video id="fullscreen-video" controls width="100%">
      <source src="/assets/green/sram-p6.mp4" type="video/mp4">
         Your browser does not support the video tag.
      </source>
    </video>
  </div>

  <div>
    <ol>
    <li>Apply flux to each pad of the capacitor's footprint.
    </li>
    <li>Using the tweezer, place a capacitor onto the footprint.
    </li>
    <li>Apply a small amount of solder to the tip of the iron.
    </li>
    <li>Using the tweezer to hold the capacitor in place, place the iron on the joint and let the solder flow.
    </li>
    <li>Apply new clean flux to the other side & repeat an application of solder.</li>
    </ol>
</div>
</div>

> Do not fuss if the capacitor is a little wonky.  But using your multimeter in continuity mode, confirm the two ends of the capacitor are not shorted. (5V & GND)


{% include disclaimer.md %}
