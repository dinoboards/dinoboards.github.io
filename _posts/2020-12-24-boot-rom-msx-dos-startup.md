---
layout: post
title:  "BOOT ROM/MSX-DOS Startup"
tags: msx rc2014
---

<p>So after what seems like a million and one flashes of the ROM chip, I now have a booting image.</p>

<p>The BIOS and disk system (CBIOS and Nextor MSX-DOS) are now working nicely together to give a command prompt.</p>


<p>I am able to run CP/M and MSX-DOS apps - although there will probably be some compatibility limits with CBIOS.</p>


<p>To enable a bootable system, without an actual floppy or hard disk, I had to create an embedded virtual disk drive within the ROM image.&nbsp; This ROM drive includes the boot executables (<em>nextor.sys</em> and <em>command.com</em>) as well as a few simple demo apps that I found online.</p>


<p>A quick summary of the things I needed to do to get the software to work:</p>


<ul><li>A fix to CBIOS for ROM initialisation, needed when booting Nextor.</li><li>A custom CBIOS image that includes extra wait states for the V9958 I/O and other minor tweaks.</li><li>For Nextor, as mentioned, added a virtual disk image driver.</li><li>And some changes to work around some design issues I have with the on-board ROM Mapper.</li></ul>


<div class="video-container"><iframe style="width: 500px; height: 281px;" src="//www.youtube.com/embed/2Wq5bvW0nfs" frameborder="0" allowfullscreen=""></iframe></div>


<p><strong>Next steps:</strong></p>


<ol><li>Fix the issue I have with the on-board ROM Mapper, to I can remove the workaround in CBIOS/Nextor.</li><li>Add some key debouncing and support for CAPS LOCK in CBIOS.</li><li>See if I can get the RC2014 SIO/2 board to work within the platform. Might have some issues with Baud rate and general performance.</li><li>Explore the possibility to write drivers for the RC2014 Floppy and HDD interface boards.&nbsp;</li><li>Continue with the other MSX boards i have coming - sound/joystick, cassette.</li><li>Will also need to explore designing/building a new board, to introduce the required wait states on M1 - as per the MSX spec. (This might be why I needed to add wait states in the CBIOS code for V9958 access)</li></ol>


<p><strong>ROM Mapper Issue:</strong></p>


<p>The issue I have with the ROM Mapper, is due to the way I have used of a single ROM chip across multiple Slots.&nbsp;&nbsp;</p>


<p>When accessing the ROM in slot 3-3, the ROM Mapper allow access to all 16k banks, the first 8 of which are the CBIOS images, and are not relevant in this slot.&nbsp;&nbsp;</p>


<p>So to access the slot's first bank, you need to write $08 to the bank selector port.&nbsp; If this is not done, then the BIOS' ROM search code will fail to see the MSX ROM marker in the slot and will not initialise and load the ROM code.</p>


<p>Now it's easy enough to add an IO write in the ROM search code in CBIOS, but for other BIOS ROM images, this will not happen.&nbsp; So to enable better compatibility I need to make sure the on-board ROM Mapper, for slot 3-3, always defaults to the correct initial bank.<br></p>
