---
layout: default
description: Powerup your retro computer with Zilog's eZ80 CPU
github_url: https://github.com/dinoboards/ez80-for-rc
hackaday_url: https://hackaday.io/project/196330-ez80-cpu-for-rc2014-and-other-backplanes
tindie_product_url: https://www.tindie.com/products/dinotron/ez80-for-rc/
lectronz_product_url: https://lectronz.com/products/ez80-for-rc
---

# eZ80 for RC

(Revision 1.10/1.11)

The *eZ80 for RC* is a CPU Module designed for the RCBus and RC2014<strong>&trade;</strong> backplanes.

The eZ80 Zilog CPU is an updated version of Z80 CPU. It comes in a few variations with many on chip facilities in addition to the basic CPU, such as flash ROM, RAM, GPIO and other IO services.

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/images/eZ80-V1.7-installed-profile-front.jpg" alt="eZ80 on RC2014" width="50%">
</div>

# What is the eZ80 CPU

The eZ80 CPU is an enhanced version of the original Z80, largely maintaining compatibility with its predecessor while offering significant improvements. It can directly address up to 16MB of memory and achieves far greater performance per clock cycle due to increased instruction efficiency and pipelining. Additionally, it integrates various on-chip peripherals such as timers, UART, SPI, I2C, and GPIOs, reducing the need for external hardware components.

While the eZ80 might appear slow and limited by today's standards, it represents, I think, an interesting evolution from the original 1970s Z80 to the modern day embedded microcontrollers.

See the Wikipedia page for basic overview of the CPU (<a href="https://en.wikipedia.org/wiki/Zilog_eZ80">https://en.wikipedia.org/wiki/Zilog_eZ80</a>)

# Key features

<ul>
  <li>Compatibility with many existing RCBus and RC2014<strong>&trade;</strong> retro modules.</li>
  <li>A fun DIY kit that can be assembled by anyone with basic soldering skills.</li>
  <li>Works in conjunction with RomWBW/HBIOS ensuring a high degree of compatibility with existing OS and applications (HBIOS, CP/M, BASIC, etc).</li>
  <li>Lots of potential for to do your own hacking and tinkering with the eZ80.</li>
</ul>

# Demo Video

Here's a video of the eZ80 for RC module running in the RC2014<strong>&trade;</strong> backplane with a few retro modules:

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMu8Gz7rkQ0?si=xwUMK4sWBoN0tg-j" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# What's included in the kit

The full kits includes everything you need.  Including the PCBs, capacitors, IC sockets, connectors, and the various ICs.  The included Programmable Logic Device (PLD) will also be flashed with the required logic.

The eZ80 CPU module will come with all the surface mounted components soldered.  You just need to solder the PCB pins and a standard 6 pin programming header.

A 20Mhz and an optional 25Mhz crystal to allow you to 'overclock' your eZ80.

# Bill Of Materials

|Quantity | Component|
|--------| -----------------------------------------|
|   2    | Right Angle 20x2 Header                  |
|   6    | 100nF                                    |
|   1    | 10uF Radial                              |
|   2    | 1uF Radial                               |
|   2    | HDR M 2.54 1x40                          |
|   2    | Shunts 1x2                               |
|   1    | 3mm Green LED                            |
|   1    | 20MHz Crystal Oscillator                 |
|   4    | 3.4mm 4.7kΩ resistor                     |
|   2    | 3.4mm 1kΩ resistor                       |
|   7    | 3.4mm 10kΩ resistor                      |
|   1    | 3.4mm 47Ω resistor                       |
|   1    | 3.4mm 470Ω resistor                      |
|   5    | 74HCT245                                 |
|   1    | ATF16V8C-7PU                             |
|   1    | TLV1117LV33DCYR**                        |
|   1    | BAT-HLD-006-SMT**                        |
|   1    | MCP130-475DI/TO                          |
|   6    | 20 POS IC DIP SOCKET                     |
|   1    | 4 POS SOCKET FOR OSCILLATOR              |
|  1     | Interface PCB for RC2014/RCBus Backplane |
|  1     | pre-assembled eZ80 CPU Module            |


\** The battery holder and 3.3V (TLV1117) DC converter are surface mounted components - but are not hard to solder with a conventional soldering iron.

# What else is needed

This kit is designed for RCBus and RC2014<strong>&trade;</strong>

* A compatible RCBus or RC2014<strong>&trade;</strong> backplane
  * recommended full 80 lane backplane
* A external RAM/ROM Module.  These 2 modules have been tested and verified:
  * [RC2014 512K RAM/ROM module](https://rc2014.co.uk/modules/512k-rom-512k-ram-module/), or
  * [SC714 – RCBus Z80 Memory Module](https://smallcomputercentral.com/sc714-rcbus-z80-memory-module/)
* As per other serial RC2014<strong>&trade;</strong> modules, you will need a means to connect the eZ80's UART to a terminal emulator.  The typical FTDI USB converters connected to your PC over USB should suffice.

* An eZ80 configured build of [RomWBW](https://github.com/wwarthen/RomWBW?tab=readme-ov-file) flashed to the ROM of the external RAM/ROM Module.

* You will also need a way to flash an image onto the eZ80's internal ROM. See next section **Flashing the internal ROM**

# Flashing the internal ROM

Before you can boot your RCBus/RC2014<strong>&trade;</strong> system, you will need to have written an image onto the eZ80's internal ROM.  For that you will need a 'programmer'.

There are 2 options for the programmer.  The Zilog's official programmer (*Zilog eZ80 Acclaim USB Smart Cable*), available from many hardware suppliers such as digikey or mouser:

* [Digikey link](https://www.digikey.com.au/en/products/detail/zilog/ZUSBASC0200ZACG/17374332)
* [Mouser link](https://au.mouser.com/ProductDetail/692-ZUSBASC0200ZACG)

## Pi Pico Programmer

An alternative and lower cost option is to use a Raspberry PI Pico.  [Click here for instructions of setting up a Pi Pico Programmer](./pi-pico-programmer)

# Caveats

* Only a limited number of RCBus/RC2014 modules have been tested to date. (Please see my [project development journal](https://hackaday.io/project/196330-ez80-cpu-for-rc2014-and-other-backplanes) describing the progress with porting and testing of various modules.)
* The ez80's SPI interface has no software support nor has it been tested yet.
* The I2C interface has limited software support at this stage.
* The main crystal oscillator (OSC1) is labelled with a frequency of 20MHz. It can actually support any frequency from 7.372MHz up to 20MHz. Overclocking is also possible; I have tested it up to 40MHz. For optimal performance, I recommend using a 25MHz crystal.
* This revision has support for a much larger battery (CR2450) and so battery life should be much improved over the old version.
* Also note, when using an oscillator other than 20Mhz, and there is no battery power, the system will not be able to adjust the speed of the serial correctly.  You would need to use a battery or build a custom firmware image.

# Images

<div class="image-gallery">
  <div class="image-column">
    <a href="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/pcb-top-v1.10.jpg" target="_blank">
      <img src="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/pcb-top-v1.10.jpg" alt="eZ80 Interface PCB Top Layer">
    </a>
    <a href="{{ site.baseurl }}/assets/ez80-for-rc/v1.11/assembled.jpg" target="_blank">
      <img src="{{ site.baseurl }}/assets/ez80-for-rc/v1.11/assembled.jpg">
    </a>
     <a href="{{ site.baseurl }}/assets/images/ez80-cpu.jpg" target="_blank">
      <img src="{{ site.baseurl }}/assets/images/ez80-cpu.jpg" alt="eZ80 CPU module">
    </a>
  </div>
  <div class="image-column">
    <a href="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/pcb-bottom-v1.10.jpg" target="_blank">
      <img src="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/pcb-bottom-v1.10.jpg" alt="eZ80 Interface PCB Bottom Layer">
    </a>
    <a href="{{ site.baseurl }}/assets/ez80-for-rc/v1.11/assembled-with-cpu.jpg" target="_blank">
      <img src="{{ site.baseurl }}/assets/ez80-for-rc/v1.11/assembled-with-cpu.jpg">
    </a>
    <a href="{{ site.baseurl }}/assets/images/ez80-kit-parts.jpg" target="_blank">
      <img src="{{ site.baseurl }}/assets/images/ez80-kit-parts.jpg" alt="ez80 for rc kit parts">
    </a>
 </div>

</div>

# Errata

V1.11
  * Added silkscreen to external bat connector
  * External battery header footprint orientation updated such that pin 1 is ground - physical orientation unchanged
  * Fix silkscreen for SPI pinout (see note below)

V1.10
  * Increased battery size to CR2450
  * Added support for a right angle header at the top for an external battery - please ensure power polarity is correct.
  * Battery holder moved to bottom side of PCB

V1.9
  * For revision 1.9 and below, see the old version of this page: [v1.9 and below](./ez80-for-rc-v1.9-and-below)

> Some of the images and videos on this page may include an older revision of the PCB.

The pinout for the SPI interface, prior to revision 1.11 was incorrect. The correct pinout from Pin 1 (at the top) down is:

<div style="padding-left: 20px;margin-top:-10px">
<ol>
<li>GND</li>
<li>SS</li>
<li>SCK</li>
<li>MISO</li>
<li>MOSI</li>
</ol>
</div>

# Jumpers/Headers

#### J1 - UART 5V Enable

* Short to enable 5V passthrough from/to the UART header (H2).

#### J2 - Bus Isolation

Reserved for future use.  Enable Bus Isolation.

* Pins 1 & 2 should be shorted together.

#### J3 - Bus Clock Enable

* Short to enable eZ80 to supply a clock signal to the RCBus/RC2014<strong>&trade;</strong> backplane.

The clock frequency will be the CPU Clock Frequency divided by 4.

#### J4 - I2C Voltage Selection

The voltage level for operating the I2C bus.

* Short pins 1 & 3 and 2 & 4 for 5V operation
* Short pins 3 & 5 and 4 & 6 for 3.3V operation.

#### H1 - GPIO

* The eZ80 GPIO's - PC1 to PC7

#### H2 - UART

* The eZ80 UART0 interface.

#### H3 - I2C

* The eZ80's I2C interface, plus its RESET and INT signals.

#### H4 - SPI

* The eZ80's SPI interface.

# Schematics

* [eZ80 Interface Module (v1.11)]({{ site.baseurl }}/assets/ez80-for-rc/v1.11/ez80-interface-schematic.pdf)
* [ez80 CPU Module (v1.4)]({{ site.baseurl }}/assets/ez80-for-rc/v1.11//cpu-module-schematic.pdf)

# eZ80 CPU Module pinout

<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/ez80-for-rc/ez80-cpu-module-pinout.png" target="_blank">
  <img src="{{ site.baseurl }}/assets/ez80-for-rc/ez80-cpu-module-pinout.png" style="width:80%;" alt="ez80 for rc kit parts">
</a>
  </div>

# Assembly Guide

Here are my recommendation for how to approach assembling and soldering the eZ80 Interface PCB and the CPU Module.

First I start with the PCB pins on the CPU PCB and the associated Round Machine Sockets on the main Interface PCB.  The PCB pins require careful attention, as they are quite small, and alignment is important otherwise you may have difficult inserting them into the sockets on the PCB.

<ol start="1">
<li>Cut the machine socket strips to the required lengths: 3 strips of 13 pins, 3 strips of 12 pins, and 2 strips of 9 pins. Be cautious when breaking the strips into the required lengths to avoid making a poor cut and losing or exposing the end pin. Using a sharp Stanley knife with some force can help achieve a clean break. Keep the knife straight.</li>
</ol>

<div class="image-gallery">
  <div class="image-column">
    <img src="{{ site.baseurl }}/assets/images/breaking-socket-strip.jpg"/>
  </div>
  <div class="image-column">
    <video style="width:100%"  controls poster="{{ site.baseurl }}/assets/images/demo-breaking-strip-poster.jpg">
      <source src="https://github.com/user-attachments/assets/44a49dc0-0513-4445-9710-4ada5918bb3e" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>
</div>

<ol start="2">
  <li>Place the sockets into the Interface PCB. Ensure the PCB is placed on foam or elevated so the sockets can sit fully in place. Do not solder them yet.</li>

  <li>Using precision tweezers, pick up one of the PCB pins and insert the shorter end into one of the sockets. Repeat this for all pins. Make sure each PCB pin is fully inserted; you should hear it click into place.</li>
</ol>

> Handle the PCB pins with care, as they can easily slip from your tweezers and flick away in any direction, including towards your eyes.

<div class="image-gallery">
  <div class="image-column">
    <img src="{{ site.baseurl }}/assets/images/closeup-of-pin.jpg" width="65%" style="display: block; margin-left: auto; margin-right:40px;"/>
  </div>
  <div class="image-column">
    <img src="{{ site.baseurl }}/assets/images/closeup-of-pins-in-socket.jpg" width="65%" style="display: block; margin-left: auto; margin-right:40px;"/>
  </div>
</div>

<div style="text-align: center;">
  <video width="400" controls poster="{{ site.baseurl }}/assets/images/inserting-pins-into-socket-poster.jpg">
    <source src="https://github.com/user-attachments/assets/a3bd98f9-aa68-448f-8ef9-192bd0f10790" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<ol start="4">
  <li>Confirm the PCB pins are gripped within the socket - they should not fall out if the socket is turned upside down.</li>
  <li>Once all the PCB pins are inserted, position the CPU module in place.<br>
  In this video, you can see the CPU PCB and the main Interface PCB connected through the PCB pins and sockets, but they are not yet soldered.</li>
</ol>

<div style="text-align: center;">
  <video width="400" height="400" controls>
    <source src="https://github.com/user-attachments/assets/6dc4e6c8-8e58-4d5f-b291-fdaf545a1b6a" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<ol start="6">
  <li>Solder the top of the CPU Module first. Then, flip it over and solder the sockets on the back of the main Interface PCB, ensuring the sockets are still fully inserted. Once both sides are soldered, remove the CPU module.</li>

<li>Solder the 2x3 (6pin) programming header on the CPU Module.  That will complete the CPU Module.</li>


<li>Before soldering the (CR2540) battery holder, you may want to place a small amount of solder on its ground pad.  This will ensure a good contact when you insert a battery.</li>

<div style="text-align: center;">
  <a href="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/pre-soldering-battery-pads.jpg" target="_blank">
    <img src="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/pre-soldering-battery-pads.jpg" width="50%" style="width: 50%;">
  </a>
</div>

<li>Solder the SMD battery holder, then the SMD 3.3V (TLV1117LV33DCYR) DC converter.  Pay attention to the orientation of the battery holder otherwise you will not be able to insert a battery.</li>

<div style="text-align: center;">
  <a href="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/battery-holder-soldered.jpg" target="_blank">
    <img src="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/battery-holder-soldered.jpg" width="50%" style="width: 50%;">
  </a>
</div>

<li>Next solder all the remaining passive through hole components, resistors, capacitors, then the sockets and headers.</li>

<div style="text-align: center;">
<img src="{{ site.baseurl }}/assets/ez80-for-rc/v1.10/assembled-without-cpu.jpg" width="85%" style="width: 85%;"/>
</div>
</ol>

> If installing this module in a case, take into account the available space and select the appropriate type for the 6-pin UART header. You can choose either a right-angle or straight header based on your requirements and preferences.

{% include disclaimer.md %}
