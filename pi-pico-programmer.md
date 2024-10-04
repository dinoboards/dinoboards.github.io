---
layout: default
title: Pi Pico Programmer
github_url: https://github.com/dinoboards/ez80-for-rc/tree/main/programmer
---

The official programmer from Zilog enables flashing and debugging of the eZ80, but at cost of over $100 USD is certainly not a cheap option.

An alternative solution, detailed here, is to use the low cost Raspberry Pi Pico (original V1) to flash your eZ80.

To make a *Pi Pico Programmer*, we need to do the following:

1. Download the software image required to run on the Raspberry Pi Pico.
2. Flash that software image onto the Raspberry Pi Pico.
3. Wire some of the pins of the Raspberry Pi Pico's to the ZDI interface of the eZ80 CPU.
5. Connect your PC to the *Pi Pico Programmer*
6. Open a terminal application, such as ExtraPuTTY, on your PC and connect to your *Pico Pi Programmer* over USB
7. Power up your eZ80 Module
8. Instruct the *Pi Pico Programmer* to flash an image onto eZ80.

### Downloading

There are 2 downloads available.  tagged Releases and general releases.  The tagged releases will have more testing conducted compared to the general releases

* <a href="https://github.com/dinoboards/ez80-for-rc/releases" target="_blank">Tagged Releases</a>
  Expand the *Assets* section under the tag release you want and download the main zip file.
* <a href="https://github.com/dinoboards/ez80-for-rc/actions/workflows/ez80-for-rc.yml?query=branch%3Amain+is%3Asuccess" target="_blank">General Releases</a>
  Click on a build, then under *Artifacts* select the **pi-pico-firmware** download.

### Flash your Pi Pico

1. Press and hold the BOOTSEL button on the Pi Pico
2. While holding BOOTSEL, plug the USB cable from the Pico into your PC
3. The Pi Pico should appear as a Mass Storage Device on your computer - look for a new drive letter.
4. Copy the `programmer.uf2` file to the root of the mounted storage device.
5. After copying, the device should reboot.
6. Confirm you can connect on serial over USB, using your favourite serial terminal application (such as PuTTY).  You will need to find the COMx number that the USB has remounted as.

### Wiring up

| Pi Pico | ZDI Interface   |
|---------|-----------------|
| GPIO 15 | ZCL             |
| GPIO 14 | ZDA             |
| GPIO 16 | RESET           |
| GPIO 17 | ZDI's PWR (3V3) |
| GND *   | GND *           |

\* Make sure you have short leads, and that the 2 ground pins are connected to ground pins of the Pi Pico.

> The Revisions V1.7 has incorrect silkscreen naming for main signal pins - (TDI -> ZDA and TCK -> ZCL)

When looking at the front of the eZ80 CPU module, the pin layout is as follows:


<div style="margin-left: 20px;">
<table style="table-layout: auto; width: auto;">
  <tr>
    <td style="white-space: nowrap;border-top: 1px solid #ffcc00;">ZDA</td>
    <td style="white-space: nowrap;border-top: 1px solid #ffcc00;">GND</td>
  </tr>
  <tr>
    <td style="white-space: nowrap;">ZCK</td>
    <td style="white-space: nowrap;">GND</td>
  </tr>
  <tr>
    <td style="white-space: nowrap;border-bottom: 1px solid #ffcc00;">RESET</td>
    <td style="white-space: nowrap;border-bottom: 1px solid #ffcc00;">3V3</td>
  </tr>
</table>
</div>

You can use the images below, and follow the colours the ensure you have correct wiring:


<div style="margin-left: 20px;">
<table style="table-layout: auto; width: auto;">
  <tr>
    <td style="white-space: nowrap;border-top: 1px solid #ffcc00;">Yellow - ZDA - GPIO 14</td>
    <td style="white-space: nowrap;border-top: 1px solid #ffcc00;">Orange - GND</td>
  </tr>
  <tr>
    <td style="white-space: nowrap;">Green - ZCK - GPIO 15</td>
    <td style="white-space: nowrap;">Red - GND</td>
  </tr>
  <tr>
    <td style="white-space: nowrap;border-bottom: 1px solid #ffcc00;">Blue - RESET - GPIO 16</td>
    <td style="white-space: nowrap;border-bottom: 1px solid #ffcc00;">Brown - 3V3 - GPIO 17</td>
  </tr>
</table>
</div>

<div class="image-gallery">
  <div class="image-column">
    <a href="{{ site.baseurl }}/assets/images/ez80-zdi-connector-left-side-example.jpg" target="_blank">
      <img src="{{ site.baseurl }}/assets/images/ez80-zdi-connector-left-side-example.jpg" alt="ZDI Left Side Wiring Example">
    </a>
    </div>
    <div class="image-column">
    <a href="{{ site.baseurl }}/assets/images/ez80-zdi-connector-right-side-example.jpg" target="_blank">
      <img src="{{ site.baseurl }}/assets/images/ez80-zdi-connector-right-side-example.jpg" alt="ZDI Right Side Wiring Example">
    </a>
  </div>
</div>


<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/images/pi-pico-example-wiring.jpg" target="_blank">
  <img src="{{ site.baseurl }}/assets/images/pi-pico-example-wiring.jpg" style="width:90%" alt="Pi Pico Example">
</a>
</div>

### Flashing your eZ80 CPU

1. Plug a USB cable between your *Pi Pico Programmer* and your main PC.
2. If using windows, identify the mounted COMx port (use Device Manager).  For linux look for the /dev/tty device.
3. Using your favourite terminal program (such as PuTTY), connect to your *Pi Pico Programmer*
You should see a message like:

```
ZDI Connection ......:    (PWR: FAIL, RST: FAIL, ZDA: FAIL, ZCL: FAIL)
```
<ol start="4">
<li>Power on your eZ80's RC2014/RCBus backplane.</li>
You should now see a message like:
</ol>
```
ZDI Connection OK:  (PWR: OK, RST: OK, ZDA: OK, ZCL: OK)
eZ80 Detected:  ID 0007 Rev AAitialisation...
Available Firmware Version: 0.1.2.0 (2024-10-03)
ZDI>
```
<ol start="5">
<li>Enter the command <code>FLASH</code></li>
<li>Your Pi Pico Programmer should have reported a completed flash of your eZ80.</li>
<li>If you have RomWBW installed on an external memory module, you should now be able to start your retro computer.
<br/>Enter <code>REBOOT</code> to start it.
</li>
</ol>

> To see your retro computer, you will need to have the UART serial connection of the Interface Module connected to a terminal application.

{% include disclaimer.md %}
