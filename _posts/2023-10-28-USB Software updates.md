---
layout: post
title:  "USB Software updates"
tags: msx
---

I have been updating the USB software over the last week or so and making some progress with support for additional hardware types.

<b>USB Keyboard</b>

I managed to get a USB keyboard to work.  At this stage, it has very limited functionality.  (arrow keys for instance don't work).  But I was able to boot and control the kit without the matrix keyboard attached - using a USB keyboard only.

Almost certainly, few games would work with the USB keyboard, but MSXDOS/NEXTOR and CP/M apps seem to work just fine.

The kit would need the PPI card (part of the keyboard kit) as without the PPI, the system will not boot.

I still need to add extra support - arrow keys, caps lock -- and I do wonder if I am able to control the keyboard's capslock LED.

<b>FTDI Serial Adapter</b>

This one is interesting.  Have a couple of USB/Serial adapters I've used to connect my PC to the original RC2014's SIO/2.  But I thought, can I now go the other way?

But this USB adapter is a vendor specific class.  That is, the USB protocol to control the adapter is not part of the USB specification - its the manufacturer's proprietary protocol.  I could not find any published specification - but there is the public Linux driver for it. The code is quite simple, and so by reviewing that code, it was quite easy to figure out how to configure the adapter and send/receive data over the serial chip.

This is still very early in the development - managed to get some experimental code to do a loop back test - (connect the TX/RX lines of the adapter).  The code confirms what it sends is also what is receives.  Have this operational at baud rates up to about 38400 - I think I can go higher!

I've only coded for the specific FTDI 232R chip - as I don't have any other chips to test and verify.  Including from other manufacturers.

Also I am starting to run out of ROM space.  All my USB code, mostly written in C using Z88DK/SDCC compiler needs to fit in about 16K.  I am at about 15K!  All part of the challenge.
