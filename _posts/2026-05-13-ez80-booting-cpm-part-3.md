---
layout: post
title: eZ80 natively booting into CP/M Part 3
tags: eZ80 Green RC2014 RCBUS CPM
---

Some progress made over the last 4 weeks.

## Keyboard driver

<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/boot.jpg"><img src="{{ site.baseurl }}/assets/posts/boot.jpg" alt="Description" style="float: right; margin-left: 15px; margin-bottom: 10px; width: 35%;"></a>

Integrated a USB keyboard driver into the firmware.  The system can now boot up with its own monitor and keyboard - no need for a serial connection to an external modern computer.

The driver will activate if a compatible USB keyboard is plugged into (via a USB HUB) the <a target="_newwindow" href="https://www.dinoboards.com.au/usb-for-rc">USB for RC</a> module.

Its looking more like a self-contained computer now.

Using CP/Ms **STAT** command, I can reconfigure the console into one of three different operating modes.

`STAT CON:=TTY:`

<p style="padding-left: 20px;margin-top:-5px">Issuing this command will direct all console input/output to the onboard <strong>UART0</strong> for serial connection.</p>

`STAT CON:=CRT:`

<p style="padding-left: 20px;margin-top:-5px">Issuing this command will change the console to use the <em><a target="_newwindow" href="https://www.dinoboards.com.au/hdmi-for-rc">HDMI for RC</a></em> module for output, and the USB keyboard for its input.  If no USB keyboard is detected at boot, this mode will fallback and use the UART0 for input.
<br/>
<br/>
The screen's text will respond to a very limited set of VT100 ESC control characters - for things like cursor movement.</p>

`STAT CON:=UC1:`

<p style="padding-left: 20px;margin-top:-5px"><strong>UC1:</strong> command is similar to <strong>CRT:</strong> - the difference is that instead of interpreting VT100 ESC characters, the <em>VDU Driver</em> is activated for all non-ASCII characters.  What's the <em>VDU Driver</em>?  This is a special driver, that I've written to be compatible as possible with Acorn's original character driver for the BBC Micro computers.
<br/>
<br/>
The Driver has support for lots of graphics commands (drawing lines, rectangles and other graphics operations).  Its primary purpose is to enable the BBCBASIC interpreter, ported to the eZ80 CPU, to have all its cool retro graphics capabilities - that is statements like <strong>MOVE</strong>, <strong>DRAW</strong>, and <strong>VDU</strong> are working now.  Lots of cool old BBCBASIC programs will soon hopefully be able to run on this platform.
<br/>
<br/>
To see a list of VDU codes, checkout this summary for <a target="_newwindow" href="https://www.riscos.com/support/developers/bbcbasic/part2/vducontrol.html">riscos's vdu implementation</a>.  I have yet to implement all of them, and their will be some subtle differences.
</p>
But default, the system will always boot with the **CON:** set to **TTY:**.  I have written a program (**IOBYTE.COM**) that change this to always boot up with a different settings:

eg:

```
IOBYTE CON:=CRT:
```

Will cause it to now always boot up in the CRT configuration.

## BBCBASIC

As mentioned above, over the last four weeks, done a lot more work on porting BBCBASIC to this platform.  I had a lot of help from Jeroen Venema.  He's been hard at work updating his port of BBCBASIC for the Agon platform - and has been kindly sharing fixes/patches to my port also.  His project can be found on github [https://github.com/envenomator/agon-bbc-basic](https://github.com/envenomator/agon-bbc-basic).

Not only has BBCBASIC received lots of languages fixes - thanks in large part to Jeroen - its also had lots of platform updates - various graphics statements and features working.  Most of those graphic enhancements come from the updates to the VDU driver in the firmware.


## Current release

I have repackaged the release for the firmware, associated apps and the Pi programmer.  They can be downloaded from the repo's releases section - [https://codeberg.org/dinoboards/ez80-for-rc/releases](https://codeberg.org/dinoboards/ez80-for-rc/releases)

The releases now also include a **manuals** directory containing documents for using and programming on this platform.  These manuals are far from complete, so I will need to update these over the coming days/weeks/months...  But they should be enough to get anyone interested in starting.

## Recommended hardware


<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/mbrot.jpg"><img src="{{ site.baseurl }}/assets/posts/mbrot.jpg" alt="Description" style="float: right; margin-left: 15px; margin-bottom: 10px; width: 35%;"></a>

Although the latest firmware will still work just fine with RomWBW on a banked memory module, to get the power of BBCBASIC and its graphics commands you need the following:

1. [eZ80 for RC CPU module](https://www.dinoboards.com.au/ez80-for-rc)
2. [Linear 2MB Memory Module](https://www.dinoboards.com.au/2mb-linear-sram)
3. [USB for RC module](https://www.dinoboards.com.au/usb-for-rc)
4. [HDMI for RC module](https://www.dinoboards.com.au/hdmi-for-rc)
5. And a compatible USB keyboard, a HDMI monitor and a USB Mass Storage device (eg: a USD Thumb Drive)


