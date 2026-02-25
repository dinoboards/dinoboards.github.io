---
layout: post
title: PI Pico Programmer Kit for eZ80
tags: Z80 eZ80 RC2014 RCBUS
---


For the eZ80 CPU to boot up it needs its internal flash ROM .... well armmm ...  flashed. &nbsp;And to do that you need a programmer.  The official *Zilog eZ80 Acclaim USB Smart Cable* can still be purchased new from places such as Mouser or Digikey - but at over $USD 100 its not super cheap.

An alternative is to use the low cost Pi Pico module.  These are small ARM powered modules; very cheap and very easy to use.

On the eZ80's product page, I have detailed how to wire one of these up and install some appropriate software.  Once wired, you can flash the eZ80's internal ROM.  See [https://www.dinoboards.com.au/pi-pico-programmer](https://www.dinoboards.com.au/pi-pico-programmer) for details.

But to make that a little easier, I have created a small PCB and kit - which can be connected with a standard 6 way IDC cable.  A little less finicky and less likely for something to go wrong.


<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-assembled-profiled.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-assembled-profiled.jpg" style="width:45%;">
</a>
</div>

Just like the Zilog programmer, you need to pay careful attention to the orientation when connecting to the eZ80 CPU module.

<div style="text-align: center;">
<a href="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-connected-closeup.jpg" target="_newwindow_">
  <img src="{{ site.baseurl }}/assets/ez80-for-rc/pi-programmer-connected-closeup.jpg" style="width:45%;">
</a>
</div>

It can now be included when purchasing the eZ80 CPU kit, or can be purchased on its own.

The eZ80 Product page is here: [https://shop.dinoboards.com.au/product/ez80-for-rc/](https://shop.dinoboards.com.au/product/ez80-for-rc/)

If you want to purchase the programmer only - its listed here: [https://shop.dinoboards.com.au/product/ez80-pi-pico-programmer/](https://shop.dinoboards.com.au/product/ez80-pi-pico-programmer/)
