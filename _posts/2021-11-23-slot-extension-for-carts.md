---
layout: post
title: Backplane and Cartridge Extension
tags: msx rc2014
---

In my previous post, I showed the progress for the Cartridge Slot extension.  I mentioned that I had yet to test with original cartridges.

Since then, I have received some game cartridges to test against.  I got a very groovy modern day game from [https://www.msxcartridgeshop.com/](https://www.msxcartridgeshop.com/), as well as the flash rom MegaFlashROM SCC+.

Also received some previously owned 1980's era games.

The game cartridges are for MSX1 machines, but the MegaFlashRom will allow me to test MSX2 type games.

The slot extender pictured in the previous posting, had my attempt to apply buffers between the RC2014 bus and the slots.  But in testing, I identified I had a flaw in the logic and was potentially generating a bus conflicts.  The game would be attempting to drive the data bus, and my buffer was also attempting to drive the bus to the cartridge - not good for the cartridge I am sure.

So I decided on the next revision to simplify things and remove the buffer chips and just connect the slots straight to the RC2014 bus.  (Why didn't I do this from the start - would have saved me a lot of headaches!)

And with the much simpler design, things are now working very well indeed, including with the cartridges from the 80s.  My RC2014 rig has a total of 10 modules, in addition to the slot extender -- So it would seem to me that the fanout for the Z80 and other modules are within their tolerances.  (I suspect if I was using an early edition Z80, rather than the new modern CMOS ones available today, things might be less reliable).

So far, I have tested the following cartridges and they seem rock solid reliable:

1. PACMAN - dated 1984

2. SALAMANDER - dated 1987

3. Hyper Sports 2 - dated 1984

4. Mutants from the Deep - dated 2021

5. MegaFlashROM SCC+

The MegaFlashROM had a conflict with the NEXTOR/MSXDOS image burnt into my onboard ROM.  I did a hack and removed that (so I only had BASIC in the onboard ROM) - and it worked just fine.  Loaded up Space Manbrow and got full perfect game play with wonderful SCC sounds!  (Furture task is to 'fix' the software compatibility with my version of NEXTOR and the Flash ROM's version)

Part of the Slot Standard requires the supply of a +12V and -12V lines.  I don't think the cartridges I have tested require this - including the MegaFlashROM.  But I have footprint on the PCB to use an optional 5V to +12V/-12V dc converter - as well as screw terminals for optional external source.

Some things I have only limited tested are:

* The supply of 12V from the onboard DC converter .  Done some probing and also used it to drive an opamp on the still under-development MSX MUSIC module - all seemed fine.
* Testing having 2 cartridges inserted at once.  I have tested running the games in Slot 1 and Slot 2 -- but have not been able to test having the two slots operating at the same time.

See below the pictures of the board installed.

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/3465721637708226952.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/3465721637708226952.jpg" width="75%"/></a>
</div>

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/3974881637708252825.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/3974881637708252825.jpg" width="75%"/></a>
</div>

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/1821341637708252762.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/1821341637708252762.jpg" width="75%"/></a>
</div>

I hope to have the slot extender board on sale in my Tindie store soon.  Stay tune for more updates.
