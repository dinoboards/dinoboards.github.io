---
layout: default
title: The Dinoboard eZ80 CPU Module
---

# The Dinoboard eZ80 CPU Module

The eZ80 Zilog CPU is an updated version of their Z80 CPU. It comes in a few variations with many on chip facilities in addition to the basic CPU such as flash ROM, RAM, GPIO and other IO services.

<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/green/cpu-module.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/cpu-module.jpg" style="width:60%;">
</a>
</div>

The green series has a specially designed CPU module.  This module is included with all the surfaced mounted components assembled and soldered.  Both the the <a href="/ez80-for-rc">ez80 for RC</a> and the <a href="/green/ozraptor">ozRaptor</a> kits use the same CPU module.

This module has some configuration options, in both the through hole pin selection and the specific Zilog part for the CPU.


## Zilog eZ80 part selection

There are 2 eZ80 chip variants available.

| CPU Part Number | Description                              |
|-----------------|------------------------------------------|
| EZ80 F93 AZ020EG  | 64KB FLASH, 4K RAM in a 100LQFP package  |
| EZ80 F92 AZ020EG  | 128KB FLASH, 8K RAM in a 100LQFP package |

As the firmware is less than 64K, and uses only 2K of on-chip RAM, both variants, when flashed with the supplied firmware, will operate identically.

Other than the noted memory capacity, both chips have identical ports and performance.  They both can run the core retro operating environments (RomWBW, CP/M, ZSDOS, etc).

> Please note, the specific eZ80 based port of MP/M, requires the F92 variant with its 8K of on-chip RAM.  The conventional Z80 based MP/M using a banked memory module is compatible with both variants.

## PCB Pins or Board-to-Board connectors

The PCB module has pin connectors for insertion to the *eZ80 for RC backplane* or the *ozRaptor baseplane*.  There are two types of connector options available:  *PCB Pins* or *Board to Board* connectors.

<table>
<tr>
<th>
Pin type
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
PCB Pins
</td>
<td>
<div style="display: flex; align-items: center; gap: 16px;">
  <img src="{{ site.baseurl }}/assets/green/pcb-pins.webp" style="width:85px;height:auto">
  <div>
    Individual plated 6.93mm long pins.
  </div>
</div>
</td>
</tr>

<tr>
<td>
Round Board to Board Connectors
</td>
<td>
<div style="display: flex; align-items: center; gap: 16px;">
  <img src="{{ site.baseurl }}/assets/green/round-board-to-board-connectors.png" style="width:85px;height:auto">
  <div>
    More conventional and much easier soldering/assembling.
  </div>
</div>
</td>
</tr>
</table>


### PCB Pins

<div style="display: flex; align-items: center; gap: 16px;">
  <a href="{{ site.baseurl }}/assets/green/pcb-pins-soldered.jpg" target="_newwindow_" style="width:350pt">
    <img src="{{ site.baseurl }}/assets/green/pcb-pins-soldered.jpg" >
  </a>
  <div>
    The PCB Pins are more expensive, harder to assembly and require careful alignment.  Additionally, if the associated sockets of the back/base plane have been over-exerted, there is a risk of poor connection.
  </div>
</div>

<br/>

### Board to Board Connectors

<div style="display: flex; align-items: center; gap: 16px;">
  <a href="{{ site.baseurl }}/assets/green/b2b-soldered.jpg" target="_newwindow_" style="width:190pt">
    <img src="{{ site.baseurl }}/assets/green/b2b-soldered.jpg" >
  </a>
  <div>
    The board to board connectors are easier to assembly by hand.  They offer the best chance of good connection.
  </div>
</div>

<br/>

### Connections to backplane and programmer

#### Board to Board connector & eZ80 for RC

The board to board connectors can be used in combination with the *eZ80 for RC* module inserted into a backplane slot spacing of 1.5cm - but only just.  It is recommend nearby modules be protected with insulation tape to prevent accidental shorting.

<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/green/b2b-gap.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/b2b-gap.jpg" style="width:80%;">
</a>
</div>

<hr/>

#### Programming connector & eZ80 for RC

The *eZ80 for RC* module requires the CPU module to be directly connected to the external programmer (via the 2x3 pins connector).  As such the pins **must** be facing up to enable direct connection to the programmer.


<div class="image-gallery">
  <div class="image-column">
<a href="{{ site.baseurl }}/assets/green/ez80-programmer-top-facing.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/ez80-programmer-top-facing.jpg" style="width:70%;">
</a>
  </div>
  <div class="image-column">
<a href="{{ site.baseurl }}/assets/green/ez80-programmer-top-side-connected.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/ez80-programmer-top-side-connected.jpg" style="width:70%;">
</a>
  </div>
</div>

<hr/>

#### Programming connector & ozRaptor

For the ozRaptor there is support for a 2x3 IDC programming connector mounted on the baseplane. As such, the CPU's modules connectors may face down (as per the other connectors).


<div class="image-gallery">
  <div class="image-column">
<a href="{{ site.baseurl }}/assets/green/ozraptor-socket.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/ozraptor-socket.jpg" style="width:70%;">
</a>
  </div>
  <div class="image-column">
<a href="{{ site.baseurl }}/assets/green/b2b-down-facing.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/b2b-down-facing.jpg" style="width:70%;">
</a>

<a href="{{ site.baseurl }}/assets/green/pcb-pins-down-facing.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/pcb-pins-down-facing.jpg" style="width:70%;">
</a>

  </div>
</div>


Or optionally, the on-board programming connectors can be skipped, and the programmer connected to the CPU module directly, as per the *eZ80 for RC* configuration.


<hr/>

### Choosing the correct configuration

Choose PCB pins if:
* You want the lowest profile as possible, particularly useful for the inline *eZ80 for RC* module.
* Happy to work and solder the very small PCB pins.
* Happy to pay the higher cost.
* happy to accept the higher risk of assembly issues.

Choose the Board-to-board connectors if:
* You are happy to have a slightly higher profile, (the *ozRaptor* baseplane module has no clearance issue).
* Want a simpler lower risk soldering/assembly process.
* Want a lower cost & less risky option.

Choose the F92 chip variant if:
* You want to write your own firmware and desired the full 128K ROM/8K RAM* onchip memory.
* You want to run my custom port of MP/M**

Choose the F93 chip variant if:
* You want to save a few bucks

\* *In combination with an external RAM module, both variants will have access of to up to 4MB of RAM.*<br/>
\*\* *My port of MP/M is customised and may not be fully compatible with the original  implementation.*

# Schematics

* [ez80 CPU Module (v1.4)]({{ site.baseurl }}/assets/green/ez80-for-rc/v1.11//cpu-module-schematic.pdf)

# eZ80 CPU Module pinout

<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/ez80-for-rc/ez80-cpu-module-pinout.png" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/ez80-for-rc/ez80-cpu-module-pinout.png" style="width:80%;" alt="ez80 for rc kit parts">
</a>
</div>
