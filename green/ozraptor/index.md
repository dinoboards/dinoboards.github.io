---
layout: default
description: eZ80 baseplane with 3 RCBus/RC2014 compatible slots
product_url: https://shop.dinoboards.com.au/product/ozraptor/
---

# eZ80 ozRaptor Baseplane

<p>Code: DB212</p>

An eZ80 powered base-plane with support for up to 4MB of zero wait state linear RAM and three RCBus/RC2014<strong>&trade;</strong> expansion slots.

<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/green/ozraptor-profile-assembled2.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/ozraptor-profile-assembled2.jpg" style="width:60%;">
</a>
</div>

<div style="text-align: center;">
  <video id="fullscreen-video" controls width="60%" preload="metadata" autoplay loop muted>
    <source src="{{ site.baseurl }}/assets/green/ozraptor-video.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<br/>

The ozRaptor is a combination of the **eZ80 for RC** and a powered RCBus/RC2014<strong>&trade;</strong> backplane.  The 4 layer PCB with the specially designed memory interface allows for higher speed operation.

The eZ80 Zilog CPU is an updated version of Z80 CPU. It comes in a few variations with many on chip facilities in addition to the basic CPU, such as flash ROM, RAM, GPIO and other IO services.

# Key features

<ul>
  <li>Compatibility with many existing RCBus and RC2014<strong>&trade;</strong> retro modules.</li>
  <li>A fun DIY kit that can be assembled by anyone with basic soldering skills.</li>
  <li>Compatible RCBus/RC2014 banked memory modules running RomWBW/HBIOS</li>
  <li>With the optional <a href="/usb-for-rc">USB for RC</a> module installed, can be booted directly into CP/M</li>
  <li>With the optional <a href="/hdmi-for-rc">HDMI for RC</a> module installed, can drive a HDMI terminal console</li>
  <li>Lots of potential to do your own hacking and tinkering with the eZ80.</li>
</ul>


# Key features compared with the **eZ80 for RC**

This kit offers a number of features compared to the eZ80 for RC module:

<ul>
  <li>High speed 0 wait/state linear RAM slots.</li>
  <li>Access to both the eZ80's 2 on chip uarts.</li>
  <li>Easier breakout for both SPI and I2C interfaces.</li>
  <li>Proper 6 pin IDC connector for programmer connection.</li>
  <li>8 on board LEDS, 1 power & 7 programmable.</li>
</ul>

# What is the eZ80 CPU

The eZ80 CPU is an enhanced version of the original Z80, largely maintaining compatibility with its predecessor while offering significant improvements. It can directly address up to 16MB of memory and achieves far greater performance per clock cycle due to increased instruction efficiency and pipelining. Additionally, it integrates various on-chip peripherals such as timers, UART, SPI, I2C, and GPIOs, reducing the need for external hardware components.

While the eZ80 might appear slow and limited by today's standards, it represents, I think, an interesting evolution from the original 1970s Z80 to the modern day embedded microcontrollers.

See the Wikipedia page for basic overview of the CPU (<a href="https://en.wikipedia.org/wiki/Zilog_eZ80">https://en.wikipedia.org/wiki/Zilog_eZ80</a>)

Zilog's eZ80 CPU is supplied in a small surfaced mounted integrated circuit. This IC is supplied soldered on a small PCB with its various pins (~100) traced to breakout PCB pins.  <a href="/green/ez80-variants">More details of this module can be found here</a>.

# What's included in the kit

The full kits includes the eZ80 CPU Module, PCB, capacitors, IC sockets, connectors, and the various ICs.  The included Programmable Logic Device (PLD) will also be flashed with the required logic.

The eZ80 CPU module will come with all the surface mounted components soldered.  You just need to solder the PCB pins.

A 20Mhz and an optional 25Mhz crystal to allow you to 'overclock' your eZ80.

The optional high speed memory expansion modules are not included - they are sold separately.

RCBus/RC2014<strong>&trade;</strong> expansion modules sold separately.

<div class="hh1">Images</div>

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/ozraptor-topside-assembled.jpg"><img src="{{ site.baseurl }}/assets/green/ozraptor-topside-assembled.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/ez80-cpu-module-topside.jpg"><img src="{{ site.baseurl }}/assets/green/ez80-cpu-module-topside.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/ozraptor-topside.jpg"><img src="{{ site.baseurl }}/assets/green/ozraptor-topside.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/ozraptor-underside.jpg"><img src="{{ site.baseurl }}/assets/green/ozraptor-underside.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/green/ozraptor-base-kit.jpg"><img src="{{ site.baseurl }}/assets/green/ozraptor-base-kit.jpg" width="90%"/></a></td>
  </tr>

</table>

<div class="hh2">Optional PI Pico Programmer Images</div>

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-pcb-front.jpg"><img src="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-pcb-front.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-pcb-back.jpg"><img src="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-pcb-back.jpg" width="90%"/></a></td>
  </tr>

  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-assembled-profiled.jpg"><img src="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-assembled-profiled.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-parts-4-3.jpg"><img src="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-parts-4-3.jpg" width="90%"/></a></td>
  </tr>

</table>


# Bill Of Materials

\* Self Source Reference are supplied as a guide only.  Please double check, in case of typo or errors in listing.

| Quantity | Component                         | Self Sourcing*                                                  |
|:--------:|-----------------------------------|-----------------------------------------------------------------|
|    2     | Right Angle 2x20 Header           | Digikey: 2057-PH2RA-40-UA-ND<br/>Mouser: 649-68020-140HLF       |
|    6     | 1x40 2.54mm Male headers          |                                                                 |
|    4     | 1x3 2.54mm Male headers           |                                                                 |
|    4     | 1x20 2.54mm Male headers          |                                                                 |
|    4     | 1x16 2.54mm Male headers          |                                                                 |
|    3     | 1x40 Round Female socket headers  |                                                                 |
|    2     | 1x6 Right Angle headers           |                                                                 |
|    13    | 0.1uF                             | Digikey: BC5137-ND<br/>Mouser: 594-K104K10X7RF53L2              |
|    1     | 10uF Radial                       | Digikey: FG18X5R1E106MRT06                                      |
|    2     | 1uF Radial                        | Digikey: FG18X5R1H105KRT06                                      |
|    3     | Shunts 1x2                        |                                                                 |
|    8     | 3mm LED                           |                                                                 |
|    1     | 20MHz Crystal Oscillator          | Digikey: MXO45HS-3C-20M000000                                   |
|    4     | 3.4mm 4.7kΩ resistor              | Digikey: MFR25SFRF52-4K7                                        |
|    6     | 4x47 Ω resistor network           | Digikey: 4608X-102-470LF                                        |
|    2     | 3.4mm 1kΩ resistor                | Digikey: MFR25SFTF52-1K                                         |
|    7     | 3.4mm 10kΩ resistor               | Digikey: MFR-12FTF52-10K                                        |
|    1     | 3.4mm 47Ω resistor                | Digikey: MFR-12FTF52-47R                                        |
|    1     | 8x470Ω resistor network           | Digikey: 4609X-101-471LF                                        |
|    1     | DC Barrel Connector               | Digikey: PJ-002B                                                |
|    1     | Tactile Switch                    |                                                                 |
|    1     | Power Terminal Block (2POS)       | Digikey: TB0010-500-02GR                                        |
|    1     | SPDT Toggle Switch                | Digikey: 200MSP1T1B2M6QE                                        |
|    1     | 74AHCT245                         | Digikey: SN74AHCT245N                                           |
|    4     | 74HCT245                          | Digikey: SN74HCT245N                                            |
|    1     | ATF16V8C-7PU                      | Digikey: ATF16V8C-7PU                                           |
|    1     | TLV1117LV33DCYR**                 | Digikey: TLV1117LV33DCYR                                        |
|    1     | BS-2450 Battery Holder            | Digikey: BS-2450                                                |
|    1     | MCP130-475DI/TO                   | Digikey: MCP130-475DI/TO                                        |
|    6     | 20 POS IC DIP SOCKET              | Digikey: 2057-ICS-320-T-ND<br/>Mouser: 571-1-2199298-6          |
|    1     | 4 POS SOCKET FOR OSCILLATOR       | Digikey: A463-ND<br/>Mouser: 535-1108800                        |
|    1     | 4 Layer PCB                       |                                                                 |
|    1     | pre-assembled eZ80 CPU Module     |                                                                 |
|    1     | Compatible DC Converter 12V to 5V | Digikey: 1951-TSR3-2450N-ND<br/>Digikey: 3182-LMS78_05-2.0RL-ND |
|    1     | IDC Connector 2x3                 | Digikey: BHR-06-VUA                                             |

\** The 3.3V (TLV1117) DC converter is a surface mounted component - but is not hard to solder with a conventional soldering iron.

### Optional Pi Pico Programmer

| Quantity | Component                 |                     |
|:--------:|---------------------------|---------------------|
|    1     | Pi Pico                   |                     |
|    1     | PCB                       |                     |
|    1     | IDC Connector 2x3         | Digikey: BHR-06-VUA |
|    2     | Slim Header - Male 1x20   |                     |
|    2     | Slim Header - Female 1x20 |                     |
|    1     | 6 way idc cable           |                     |


# What else is needed

* A means to flash an image onto the eZ80's internal ROM. See next section **Flashing the internal ROM**
* As per other serial RC2014<strong>&trade;</strong> modules, you will need a means to connect the eZ80's UART to a terminal emulator.  The typical FTDI USB converters connected to your PC over USB should suffice.

There are 2 operating modes: RomWBW booting or Direct USB Storage Booting.

### For direct booting from USB storage
* The <a href="/usb-for-rc">USB for RC</a> module.
* The <a href="/green/fast-linear-ram">2MB Fast RAM Module</a> <small>(Recommended)</small> or the standard speed <a href="/2mb-linear-sram">RCBus 2MB Linear SRAM Module</a>.

### For conventional RomWBW Booting

A external RAM/ROM Module.  These 2 modules have been tested and verified:
  * <a href="https://rc2014.co.uk/modules/512k-rom-512k-ram-module/"  target="_newwindow">RC2014 512K RAM/ROM module</a>, or
  * <a href="https://smallcomputercentral.com/sc714-rcbus-z80-memory-module/" target="_newwindow">SC714 – RCBus Z80 Memory Module</a>
  * An eZ80 configured build of [RomWBW](https://github.com/wwarthen/RomWBW?tab=readme-ov-file) flashed to the ROM of the external RAM/ROM Module.


# Flashing the internal ROM

Before you can boot your system, you will need to have written an image onto the eZ80's internal ROM.  For that you will need a 'programmer'.

There are 2 options for the programmer.  The Zilog's official programmer or the optional Pi Pico Programmer.

*Zilog's eZ80 Acclaim USB Smart Cable* is available from many hardware suppliers such as digikey or mouser:

* [Digikey link](https://www.digikey.com.au/en/products/detail/zilog/ZUSBASC0200ZACG/17374332)
* [Mouser link](https://au.mouser.com/ProductDetail/692-ZUSBASC0200ZACG)

## Pi Pico Programmer

An alternative and lower cost option is to use a Raspberry PI Pico.  If you have a Pi Pico handy, you can, via some jumper wires, connect it directly - or you can get the optional eZ80 Pi Pico Programmer kit.

[Click here for instructions of setting up a Pi Pico Programmer](/pi-pico-programmer)

# Caveats

* Only a limited number of RCBus/RC2014 modules have been tested to date. (Please see my [project development journal](https://hackaday.io/project/196330-ez80-cpu-for-rc2014-and-other-backplanes) describing the progress with porting and testing of various modules.)
* The SPI & I2C interface has limited software support at this stage.
* The main crystal oscillator (OSC1) is labelled with a frequency of 20MHz. It can actually support any frequency from 7.372MHz up to 20MHz. Overclocking is also possible; I have tested it up to 40MHz. For optimal performance, An optional 25MHz crystal can be included.  System has been tested running at 30Mhz, with fast RAM still running at zero wait states.
* Also note, when using an oscillator other than 20Mhz, and there is no battery power, the system will not be able to adjust the speed of the serial correctly.  You would need to use a battery or build a custom firmware image.


# Jumpers/Headers

#### J1 - Bus Clock Enable

* Short to enable eZ80 to supply a clock signal to the RCBus/RC2014<strong>&trade;</strong> backplane.

  (The clock frequency is the CPU's clock frequency divided by 4)

#### J2 - I2C Voltage Selection

The voltage level for operating the I2C bus.

* Short pins 1 & 3 and 2 & 4 for 5V operation
* Short pins 3 & 5 and 4 & 6 for 3.3V operation.

#### H1 - GPIO

* The eZ80 GPIO's - PC1 to PC7

#### H2 - UART0

* The eZ80 UART0 interface.

#### H3 - I2C

* The eZ80's I2C interface, plus its RESET and INT signals.

#### H4 - SPI

* The eZ80's SPI interface.

#### H5 - UART1

* The eZ80 UART1 interface.

#### H6 - Optional

* Not connected.  Can be used for ad-hoc bodge connections.

#### H7 - Optional

* Optional header (solder on PCB's bottom face or bodged to H6)

  (PC4..PC7), (PD5..PD6) and ground.


# Schematics

* [Main module (v1.11)]({{ site.baseurl }}/green/ozraptor/schematic.pdf)
* [ez80 CPU Module (v1.4)]({{ site.baseurl }}/assets/ez80-for-rc/v1.11//cpu-module-schematic.pdf)

# eZ80 CPU Module pinout

<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/ez80-for-rc/ez80-cpu-module-pinout.png" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/ez80-for-rc/ez80-cpu-module-pinout.png" style="width:80%;" alt="ez80 for rc kit parts">
</a>
</div>

# Assembly Guide

Here are my recommendation for how to approach assembling and soldering the eZ80 Interface PCB and the CPU Module.

The notes regarding soldering the small PCB pins can be ignored if using the conventional Board to Board connectors.

#### NOTE 1 - SEE EZ80 FOR RC

The assembly guide for the <a href="/ez80-for-rc#assembly-guide">eZ80 for RC</a> is worth reviewing. The notes below do detail a different approach to soldering PCB pins.

#### NOTE 2 - The SMD 3.3V DC Converter (TLV1117LV33DCYR)

Recommend this small SMD component is soldered first.

#### NOTE 3 - START WITH THE ROUND SOCKETS

Cut the machine socket strips to the required lengths: 3 strips of 13 pins, 3 strips of 12 pins, and 2 strips of 9 pins. Be cautious when breaking the strips into the required lengths to avoid making a poor cut and losing or exposing the end pin. Using a sharp Stanley knife with some force can help achieve a clean break. Keep the knife straight.

<div class="image-gallery">
  <div class="image-column">
    <img src="{{ site.baseurl }}/assets/images/breaking-socket-strip.jpg" style="width:75%"/>
  </div>
  <div class="image-column">
    <video style="width:80%"  controls poster="{{ site.baseurl }}/assets/images/demo-breaking-strip-poster.jpg">
      <source src="https://github.com/user-attachments/assets/44a49dc0-0513-4445-9710-4ada5918bb3e" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>
</div>


#### NOTE 4 - PCB Pin

If you are soldering the small PCB Pins, its important to ensure alignment.  The recommended approach is to:

1. first solder the socket into the baseplane - ensuring they are all flat and square.

2. Using tweezer, insert 2 or 3 pins into the socket (as per NOTE 5). Confirm the PCB pins are gripped within the socket - they should not fall out if its turned upside down.

3. Place the CPU Module into place.  Solder those 2 or 3 pins.  Carefully remove the CPU Module, insert some more pins, then repeat the process.

If you attempt to place all pins at one, you may find it very difficult to align the PCB Module over the pins, as tolerances are kept very tight.

#### NOTE 5 - PCB Pin insertion

Using precision tweezers, pick up one of the PCB pins and insert the shorter end into one of the sockets.  Make sure each PCB pin is fully inserted; you should hear it click into place.

> Handle the PCB pins with care, as they can easily slip from your tweezers and flick away in any direction, including towards your eyes.

<div class="image-gallery">
  <div class="image-column">
    <img src="{{ site.baseurl }}/assets/images/closeup-of-pin.jpg" width="65%" style="display: block; margin-left: auto; margin-right:40px;"/>
  </div>
  <div class="image-column">
  <video width="400" controls poster="{{ site.baseurl }}/assets/images/inserting-pins-into-socket-poster.jpg">
    <source src="https://github.com/user-attachments/assets/a3bd98f9-aa68-448f-8ef9-192bd0f10790" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  </div>
</div>


#### NOTE 6 - ORIENTATION OF PROGRAMMING PINS

The ozRaptor board fully supports the programming pins (2x3 connector top right of PCB Module).

If your CPU Module has the programming pins already soldered and facing up, you may want to:

1. Desolder them and solder pcb pins facing down, or,
2. Skip soldering the associated sockets on the baseplane.

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

<a href="{{ site.baseurl }}/assets/green/ez80-programmer-top-facing.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/green/ez80-programmer-top-facing.jpg" style="width:70%;">
</a>

  </div>
</div>

#### NOTE 7 - 2x3 PROGRAMMING PCB PINS

The holes sizes for the programming pins in the eZ80 CPU module are larger, to accommodate a standard header.  As such, if you are soldering the small PCB pins, be careful in the application of solder, so at not to 'solder to the sockets'.

#### NOTE 8 - FAST RAM HEADERS

The fast ram headers are comprised of 2 sets of 3 header strips (20 pins, 3 pins and 19 pins).  You may want to pay attention to ensuring consistent alignment when soldering.

There is sufficient tolerances should a small mis-alignment occur - but you may find it visually annoying if they are not all straight and consistent.

> If you use a fast RAM module to jig the headers into place, make sure you do not attempt to remove the module from the sockets until all connections have been soldered.

#### NOTE 9 - COMPLETING SOLDERING

After the CPU module and sockets are fully soldered, you can now proceed to solder the rest of the board from lowest height to largest height components.

<br/>

### Pi Programmer Assembly

#### NOTE 1 - SPECIAL CARE WITH SOLDERING LOW PROFILE HEADERS

> With kits supplied with the low profile slim 1x20 headers, special care is recommend with the soldering of the female headers to the PCB.  There is a risk that when soldering, solder will flow down into the header - and thus prevent a good fit with the associated male headers.

#### NOTE 2 - PAY ATTENTION TO IDC SOCKET ORIENTATION

> Ensure you solder the 6 pin IDC socket in its correction orientation.  See the PCB's silkscreen layout.  Incorrect orientation may result in damaging your eZ80 CPU.

[Click here for more details](/pi-pico-programmer)

{% include disclaimer.md %}
