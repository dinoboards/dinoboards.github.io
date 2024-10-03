---
layout: default
title: eZ80 for RC
---

### Raspberry Pi Pico Programmer for the eZ80

The official programmer from Zilog enables flashing and debugging of the eZ80, but at cost of over $100 USD is certainly not a cheap option.

An alternative solution, detailed here, is to use the low cost Raspberry Pi Pico (original V1) to enable flashing of the eZ80

To make a Pi Pico Programmer, you need to do the following:

1. Download the software image required to run on the Raspberry Pi Pico.
2. Flash that software image onto the Pi Pico.
3. Wire some of the pins of the Pi Pico's to the ZDI interface of the eZ80 CPU.
5. Connect your PC to the Pi Pico
6. Open a terminal application, such as ExtraPuTTY and connect to your Pico Pi over USB
7. Power up the eZ80 Module
8. Instruct the Pi Pico to flash an image onto eZ80.

### Details

todo

### Wiring Diagram


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

TODO: Add a back/home button
