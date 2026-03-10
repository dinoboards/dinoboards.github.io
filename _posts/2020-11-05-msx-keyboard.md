---
layout: post
title:  "MSX Keyboard"
tags: msx rc2014
---

Now have a keyboard.

My initial design had a few flaws, but with some hacking, was able to get a fully functioning keyboard working.

I used the keyboard driver within CBIOS (https://sourceforge.net/projects/cbios/) to build a keyboard driver for RomWBW hbios' implementation.  This give me some confidence that my keyboard is compliant and meets msx requirements.

As for the RTC, the initial version of the driver is sitting on my RomWBW fork (https://github.com/vipoo/RomWBW/blob/dean/dev-msxkeyboard/Source/HBIOS/msxkeyb.asm)

I can now boot up my rc2014, using TMS 9918 video and standalone keyboard. No serial interface required.

Its nice to finally be able to use cp/m and microsoft basic with a proper keyboard and a wonderful 40 column display.

The keyboard using standard cherry switches

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/1502561604573667572.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/1502561604573667572.jpg" width="75%"/></a>
</div>

some nice retro keycaps

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/6692091604573668608.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/6692091604573668608.jpg" width="75%"/></a>
</div>

Some 'hacking' to make it work!

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/8212551604573661577.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/8212551604573661577.jpg" width="75%"/></a>
</div>

In my searching, it seems most keyboards use a 4-to-10 decoder to create the scan rows - i changed this to use 2 3-8 decoders (74HC138).  It seems a little easier and cheaper to use this IC - I have lots of them.

