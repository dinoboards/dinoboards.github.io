---
layout: default
title: USB for RC
description: Let your Z80 talk directly to enumerate and operate many different types of USB devices
tindie_product_url: https://www.tindie.com/products/dinotron/usb-for-rc/
github_url: https://github.com/dinoboards/ez80-for-rc
hackaday_url: https://hackaday.io/project/196330-ez80-cpu-for-rc2014-and-other-backplanes/log/237947-belated-progress-report
is_new: true
---

# USB for RC <img src="{{ site.baseurl }}/assets/new.png" style="width:36px; margin-left: 8px; position:absolute"/>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/usb-for-rc/profile.jpg" width="70%"/>
</div>

Bring your RCBus/RC2014 build into the 90's with true native support for Universal Serial Bus.  Enable the Z80 drivers in a new RomWBW ROM images and then connect your system to:

* USB Hubs
* USB flash devices
* USB magnetic mechanical hard disks
* USB 3.5" Floppy drives
* USB Keyboards
* And Many more types to come..

There are plans to update the software to further improve keyboard support, and add support for other USB devices, such as USB to Centronics adapters for dot matrix printers, ethernet adapters, and other useful USB devices.

# General Description

This is a kit based on the CH376 USB Module.

The CH376 module provides a high level interface for connecting to the most common mass storage devices, but that interface is limited and will not work through hubs.  The CH376 module also supports driving the USB communication directly, enabling the ability to operate any compatible USB device.  The drivers I originally wrote for MSX-DOS have been ported to RomWBW.  These drivers, written in C for the Z80, fully support enumerating and discovering the attached USB devices, and enable the Z80 to understand the 'USB Protocol' directly.

# Key features

* USB 1.1/2.0 compatible (although certainly not certified)
* Tested with a large assortment of flash drives, HDD, Floppy, and hubs.
* Drivers written in C so a little more accessible than pure Z80 assembly
* Individually programmable LEDs to indicate USB operation

# Images

<table>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/usb-for-rc/pcb-assembled.jpg"><img src="{{ site.baseurl }}/assets/usb-for-rc/pcb-assembled.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/usb-for-rc/connected.jpg"><img src="{{ site.baseurl }}/assets/usb-for-rc/connected.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/usb-for-rc/pcb-top.jpg"><img src="{{ site.baseurl }}/assets/usb-for-rc/pcb-top.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/usb-for-rc/pcb-bottom.jpg"><img src="{{ site.baseurl }}/assets/usb-for-rc/pcb-bottom.jpg" width="90%"/></a></td>
  </tr>
</table>


# Testing Status

The correct interfacing with any USB device is mostly limited by the software drivers that have been specifically written to enable appropriate support under MSX-DOS/NEXTOR.  So any limitation or issue can probably, once identified, be corrected with a software update.

There has certainly not been any USB certification conducted.  Just lots of manual testing by me.  There are possibly still things in the software that are not following the rules.

Hot swapping of devices is not supported.  Insert your USB devices then power on or reset.  You can change floppies, but unpluging and re-inserting any USB device will require a reboot

> Please note, that due to some timing limitation of the CH376 mode, some devices or the module itself, may fail to get detected on initial boot/power-on.  Hit the reset button and it should be detected fine.

There are 4 main USB classes implemented to date:
* enumeration/discovery of devices through USB hubs.
* UFI which is used by floppy drives
* SCSI which is used by flash, HDD and other large storage devices
* HID for a keyboard (requires an appropriate video module to be installed and enabled)

## SCSI: Flash/Thumb and HDD drives

<table>
<tr>
<td width="80%">

<ul style="padding-left: 20px;">
<li>I have tested against 9 different Thumb/flash drives of varying sizes.</li>
<li>Tested against a couple of external magnetic hard disk drives.</li>
<li>A couple of modern USB keyboards</li>
</ul>

</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/flash-drives.jpg" height="100px" />
</td>
</tr>
</table>

## UFI: Floppy drives

<table>
<tr>
<td width="80%">

<ul style="padding-left: 20px;">
<li>I have tested against 3 USB 3 1/2" floppy drives.  They each operated slightly differently. For the most part they all work.</li>
<li>I did experience some specific compatibility issues with these drives - but so did windows, so I suspect its more limitations of the specific drives.</li>
</ul>

</td>
</tr>
</table>

<table>
<tr>
<td width="60%">

<strong>TEAC drive - purchased on ebay.  Seems to be the most common available today</strong>

<ul style="padding-left: 20px;">
<li>Recommended</li>
<li>Can format, read and write to 720K and 1.44MB (Please note formatting is not currently supported on RomWBW nor CP/M)</li>
</ul>

</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/teac-top.jpg" height="100px" />
</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/teac-back.jpg" height="100px" />
</td>
</tr>
<tr>

<td width="60%">

<strong>IBM drive - Seems to be an 'older' TEAC drive internally</strong>

<ul style="padding-left: 20px;">
<li>can read and write 720K and 1.44Mb disk</li>
<li>formatting was unreliable - 720K formatted does not seem to be supported (Please note formatting is not currently supported on RomWBW nor CP/M)</li>
</ul>

</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/ibm-top.jpg" height="100px" />
</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/ibm-back.jpg" height="100px" />
</td>
</tr>
<tr>
<td width="60%">

<strong>Imation drive - Old drive</strong>

<ul style="padding-left: 20px;">
<li>read/write 720K disk ok</li>
<li>does not support HD 1.44MB</li>
<li>formatting not tested (Please note formatting is not currently supported on RomWBW nor CP/M)</li>
</ul>
</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/imation-top.jpg" height="100px" />
</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/imation-back.jpg" height="100px" />
</td>
</tr>
</table>

## USD Hub

All but one of the hubs tested works.  All but one of the hub seemed to have been 'certified'.

<table>
<tr>
<td width="60%">

<strong>Orico 4 Port USB 3.0 Transparent Hub</strong>

<ul style="padding-left: 20px;">
<li>Highly Recommended</li>
<li>externally powered which is really recommend if using floppy disks</li>
</ul>

</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/orico-hub.jpg" height="100px" />
</td>
</tr>
<tr>

<td width="60%">

<strong>Generic USB hubs</strong>

<ul style="padding-left: 20px;">
<li>all tested ok</li>
</ul>
</td>
<td>
<img src="{{ site.baseurl }}/assets/cassette-and-usb/cheap-hub-1.jpg" height="100px" />
<img src="{{ site.baseurl }}/assets/cassette-and-usb/cheap-hub-2.jpg" height="100px" />
<img src="{{ site.baseurl }}/assets/cassette-and-usb/cheap-hub-3.jpg" height="100px" />
</td>
</tr>

</table>
<!--
## Printer adapters

* Tested with 2 USB to Centronics adapters from ebay.  Both seem to use the same chips internally.

* Tested with one 9pin dot matrix printer.

<table>
<tr>
<td width="60%">
<img src="{{ site.baseurl }}/assets/cassette-and-usb/printer-1.jpg" height="100px" />
<img src="{{ site.baseurl }}/assets/cassette-and-usb/printer-2.jpg" height="100px" />
</td>
</tr>

</table>

### Printer driver (ROM builds after 2023-11-06)
> For ROM builds after 2023-11-06, the installation of a USB printer driver is required.  (The driver is no longer included in the embedded ROM image)
>
> The are 2 executables needed to install the driver (`SERVICE.COM` and `PRNT.SYS`).
> In your AUTOEXEC.BAT file, you need to add this section:
>
> ```
> SERVICE=PRNT.SYS
> ```
> If no printer or USB is detected during the install - then no driver will be installed.  If installation is successful, you will see the following output:
>
> ```
> PRNT.SYS:    INSTALLED
> ``` -->


# What's included in this kit

The full kits includes everything you need (PCB, capacitors, IC sockets, CH376S module, connectors, and the ICs).  And an optional small Flash drive that's been tested and confirmed to work.

# Bill of Materials

|Count   | Name  |
|:------:|-------|
| 4      |  0.1uF                     |
| 1      |  220uF                     |
| 3      |  1N4148                    |
| 2      |  3mm	leds                  |
| 1      |  4.7kΩ (3mm)               |
| 2      |  470Ω Resistor (3mm)       |
| 1      |  CH376S USB Module         |
| 1      |  74HCT138                  |
| 1      |  74HCT32                   |
| 1      |  74HC74                    |
| 2      |	Right Angle 1x20 Header   |
| 2      |	14 POS IC SOCKET          |
| 1      |	16 POS IC SOCKET          |
| 1      |	512MB USB Flash Drive (optional)     |


# What else do I need to make this work?

* A working RC2014/RCBus system
* An updated RomWBW ROM image configured to enable the CH376 'native' driver.

## Updating RomWBW

You will probably need to update your image of RomWBW.  Please refer to the official instructions for updating and flashing the ROM at [https://github.com/wwarthen/RomWBW](https://github.com/wwarthen/RomWBW)

The configuration changes you will need to set are describe below:

```
CHENABLE       .SET FALSE ; DISABLE THE CH375 FLASH ONLY DRIVER
CH0USBENABLE   .SET FALSE ; DISABLE THE CH375 FLASH ONLY DRIVER
CH1USBENABLE   .SET FALSE ; DISABLE THE CH375 FLASH ONLY DRIVER

CHNATIVEENABLE .SET TRUE  ; CH376: ENABLE CH376 NATIVE USB DRIVER
CHSCSIENABLE   .SET TRUE  ; CH376: ENABLE CH376 NATIVE MASS STORAGE DEVICES (REQUIRES CHNATIVEENABLE)
CHUFIENABLE    .SET TRUE  ; CH376: ENABLE CH376 NATIVE UFI FLOPPY DISK DEVICES (REQUIRES CHNATIVEENABLE)
CHNATIVEFORCE	 .SET	TRUE	; CH376: DISABLE AUTO-DETECTION OF MODULE - ASSUMES ITS INSTALLED
```

> At this time, the USB drivers are not on the mainline (master) of RomWBW - you can use my fork of the project [https://github.com/dinoboards/RomWBW/tree/dean-ch376-usb-native-5](https://github.com/dinoboards/RomWBW/tree/dean-ch376-usb-native-5) to build an image for your system.

As the CH376 native driver code size is quite large compared to many other HBIOS drivers, you may need to disable other drivers in your configuration (such as `IDEENABLE`, `FDENABLE`, `SDENABLE`)

To enable the USB Keyboard, you will also need a TMS/V9958 video adapter installed and its driver enabled.  The keyboard driver is a sub part of the general CRT interface. The keyboard does not replace the serial input.

```
TMSENABLE    .SET TRUE           ; TMS: ENABLE TMS9918 VIDEO/KBD DRIVER (TMS.ASM)
TMSMODE      .SET TMSMODE_MSXUKY ; TMS: DRIVER MODE: TMSMODE_[SCG|N8|MSX|MSXKBD|MSXMKY|MBC|COLECO|DUO|NABU|MSXUKY]
                                 ; USB KEYBOARD WITH MSX COMPATIBLE VIDEO
TMSTIMENABLE .SET TRUE           ; TMS: ENABLE TIMER INTERRUPTS (REQUIRES IM1)

USBKYBENABLE .SET TRUE           ; USB KEYBOARD DRIVER
```

Once booted into CP/M over serial, you can type the following command to switch to the Video output and keyboard input:

```
STAT CON:=CRT:
```

> Please note the software driver for the Keyboard is still under development - and not all keys will be mapped, and characters may get dropped if you type too fast.

# Port Mapping

#### The board use the following IO addresses

| Port |	Description|
|------|-------------|
| $88	(r/w) | CH376 data port  |
| $89	(r/w) | CH376 command port  |
| $8A (w) | LED control (bit 0 and 1 only) |
| $8B (w) | mirror of $8A |


<!-- # Accessing a USB printer.

The system will on boot, report if it has detected the presence of a USB to Centronics printer adapter.  Assuming you have connected the adapter to a simple dot matrix or compatible printer, you can use the standard MSX-DOS commands/process to send text to the printer.

For example, the following MSX-DOS command will send the file, `MYTEXT.TXT`, file to the printer.

```
COPY MYTEXT.TXT PRN
``` -->

# Resources

* Schematic: [schematic](usb-for-rc/schematic.pdf)
* Datasheet: [CH376](assets/ch376ds1.pdf)

{% include disclaimer.md %}
