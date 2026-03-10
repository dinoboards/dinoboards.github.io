---
layout: post
title:  "Software for the MSX on RC2014"
tags: msx rc2014
---

<p>I received and assembled the Memory boards.&nbsp; Now i just need some software to put on it!</p>


<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/1956771608350493367.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/1956771608350493367.jpg" width="75%"/></a>
</div>


<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/8715191608350528523.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/8715191608350528523.jpg" width="75%"/></a>
</div>


<p>Over the last couple of weeks, I have been working on the software platform.&nbsp;&nbsp;</p>


<p>Many modern MSX solutions (kits/emulators) use ROM images extracted from one of the original computers.&nbsp; These ROM images are easy to find and download.<br></p>


<p>I could follow this approach for my build, but I prefer a more&nbsp;open-source and legitimate approach.&nbsp;</p>


<p>Having access to the source code, will allow me to debug and verify the hardware, and be a good starting point to add additional features, such as support for RC2014's serial and IDE boards.</p>


<p>There are 2 key projects that I have been exploring:</p>


<p>1. <a href="https://github.com/cbios/cbios">CBIOS</a>- An open source compatible MSX BIOS.&nbsp; It does not include a Basic Interpreter.&nbsp; It's distributed with many of the MSX emulators with a primary focus to enable the loading of various ROM images (typically games).&nbsp; My fork of this project is at:&nbsp;<a href="https://github.com/dinoboards/cbios/tree/dean/spike">https://github.com/dinoboards/cbios/tree/dean/spike</a></p>


<p>2. <a href="https://github.com/Konamiman/Nextor">Nextor</a>- This is a fascinating project.&nbsp; It is based on the original MSX-DOS 2 source code - and now officially opened source and apparently ok to distribute.&nbsp; MSX-DOS is a CP/M compatible OS,&nbsp; that is kind of half way between CPM and MS-DOS.&nbsp; An interesting story within the history of the early home computer OS development.&nbsp; My fork of this project is at:&nbsp;<a href="https://github.com/dinoboards/Nextor">https://github.com/dinoboards/Nextor/tree/dean/spike</a></p>


<p>These two projects can be used as a foundation for the boot ROM.&nbsp; They do require a bit of work to meet my needs.&nbsp; The key enhancements needed were:</p>


<p>1. Create a makefile build system for building nextor in linux.</p>


<p>2. Tweaks/fixes to get nextor and cbios working together.</p>


<p>3. Add an embedded virtual disk image within the nextor rom image - so that the key utilities are available on boot - much like how RomWBW cp/m boots up with a ROM and RAM disk. (Nextor already has support for RAM Disk.)</p>


<p>4. Other fixes/enhancements required to boot up on the rc2014 hardware.&nbsp;</p>


<p>I have been able to get this all working within an emulator - so the next step is to flash a ROM and power up!</p>
