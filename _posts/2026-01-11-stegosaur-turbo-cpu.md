---
layout: post
title: Green Stegosaur Turbo CPU for RC2014/RCBus
tags: Green stegosaur msx turbo-cpu
---

Next module to be downsized, is the Turbo CPU module.

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/turbo-cpu/images/profile.jpg"><img style="width:80%" src="{{ site.baseurl }}/stegosaur/turbo-cpu/images/profile.jpg" alt="Assembled Profiled" width="100%"/></a>
</div>

I manage to reduce the PCB size, by removing the on-board slow clock, and relying on an external slow clock source, such as a RC2014 Dual Clock module, or the RGB Video Module.

I am particularly proud of this module -- as it was perhaps the first design I did that wasn't so much based on stock MSX schematics.

For those that don't know - the Turbo CPU module runs a standard Z80 40 pin chip (Z84C0020PEG), at up to 20Mhz.  Its not overclocking it - nor does it require the backplane clock to run at 20Mhz.  It dynamically switches the clock of the CPU between the bus-clock and its 20Mhz turbo boost speed.

The clock speed of the CPU is switched to the bus-clock, when the IOREQ line goes low.  It holds the processor at the 'slow' bus clock for 31 slow clock ticks.

This means when the processor is communicating with any I/O device, its running at the modest bus clock speed - to ensure compatibility.  But when its just 'processing' or reading/writing to memory - it runs at its boost speed.

This turbo boost process gives it a lot of compatibility with existing devices - but can really improve those very slow IX/IY+n operations a lot.

It was an interesting challenge, to do the clock switch - can't just do an immediate switch between the two clocks.  You have to ensure when it transitions from one clock to the other, that its not done too quickly, that we end up momentarily having a super high frequency sent to the CPU's clock input; the 2 clock sources (20Mhz fast and the standard bus clock) are not in phase - so when switching it would glitch unless it waits.  When transitioning, the clock is 'stretched' a little until we sync up with the other clock.

This module will work just find as a replacement for the stock RC2014/RCBus Z80 processor modules as well as a perfect speedy CPU solution for the MSX2 configuration.

I have more details of the module and schematic up on my site now: [https://www.dinoboards.com.au/stegosaur/turbo-cpu/](https://www.dinoboards.com.au/stegosaur/turbo-cpu/)

And its listed on my shop for sale as a kit [https://shop.dinoboards.com.au/product/stegosaur-turbo-cpu/](https://shop.dinoboards.com.au/product/stegosaur-turbo-cpu/)


