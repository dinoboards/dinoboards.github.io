---
layout: post
title:  "Progress Update"
tags: msx
---

Its been a while since I posted here about the project.

I have been really struggling to find the time (the usual suspects, work, life etc)

First, I want to express my thanks to everyone who has taken an interested in my little project, liked/commented here on Hackaday or purchased some of my kits.   Your encouragement and support is fantastic and much appreciated.

And with that, I was finally able to dust off the soldering iron and get back into developing and updating stuff.

I am working on 3 main tasks at the moment.

* A new revision for the **Video Module** to support the **V9938** chip.
* A new revision of the **MSX Music** module that reduces the idle background noise caused by nearby digital signals.
* And a new kit under development, the **USB Module** (based on the CH376 module).
* And I also managed to restock my Tindie store.

**V9938 version of the Video Module**

When I was restocking my store recently, I needed to source some new V9958 chips.  I found that the price for the chip has gone up a lot - at about $45-$50 USD.  That seems like its doubled in price since I started this project.  This would have been a better investment than an AI company!

But the previous generation video chip, the V9938, still seems to be generally easy to source and at a lower price.

One day though, these chips will become virtually impossible to get.

Given this, I decided to update the Video kit to enable support for the V9938. (I guess that makes it more retro!).

I also redesigned the power filtering and re-arrange the layout a bit to help reduce noise leaking into the video signal paths.

The V9938 has some minor differences to the V9958.

It has features that were removed in the V9958, such as a mouse interface (I don't think was used very much) and direct support for a composite video out.

Graphically the V9938 does not support the 'near true' colour screen mode.  It also lack the support for smooth horizontal scrolling that some games took advantage of.  But it still offers a very similar capability, including all the other screen modes, sprites and memory support.  Its programmed in the same way, so the software and games just work.

Hopefully I can have this new revision listed in my Tindie store soon - with schematic and more details to follow.

**New Revision of the MSX Music**

One of the things I was less than pleased with this kit, is its susceptibility to the digital noise and nearby EMF interference, causing buzzes and hums to be heard when no music was playing.  This was especially noticeable when running the Z80 at the 20Mhz speed. After experimenting with a few inductors and capacitors, I managed to isolate a good chunk of the noise.  Its now much better.

I am perhaps starting to run the YM2413 audio chip at closer to its minimum power specification.  The low pass filter applied to isolate the digital noise, does drop the voltage a little.  If you combine perhaps a slightly lower than 5V source, some general loss in the backplane power rail - we start to approach the minimum spec voltage of 4.75.  But I think there is enough headroom to ensure its always above spec.  I have done lots of testing, and all seems rock solid reliable.

**The USB Module**

This has been my main focus over the last few weekends.  The amount of effort applied to get this working is rather ridiculous when I think about it.  I was beginning to wonder if I was insane trying to get this to work.  Most of the effort is in the software.  I have had to learn a lot about USB protocols as well as the specific USB floppy and thumb drive protocols.   Not to mention figuring out how to enumerating devices plugged into hubs.

The CH376 module seems capable enough, but the documentation did leave me pondering a lot.

Trying to fit all this USB protocol logic into a page of the ROM (approx: 8K) was also a challenge.  The poor Z80 was never meant for such heights.  But it continues, like me I suppose, to learn new tricks!

So far, I have implemented support for USB Hubs, up to four storage devices (mass storage thumb drives and other USB HDDs), floppy drives.  And just last week, I managed to get my MSX to print to a 9 pin dot matrix Centronics printer, using a USB to Centronics adapter cable.  So now my lab echoes with sounds of impact printing.  Oh Joy!

The current PCB requires a few bodge wires, so I need to get a new PCB manufactured and tested.  Stay tune for more details on its development.

If you have read all the way to hear, thanks - i hope you found it interesting...

I will try and keep updating the journal and provide more details of the project updates.
