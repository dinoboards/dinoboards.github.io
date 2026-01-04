---
layout: post
title: New Series of modules
tags: Green stegosaur msx v9958
---

It's a new year, and I have some new modules under development.

I have started to look at updating my Yellow MSX series with new PCB designs that fit the more conventional RC2014/RCBus height of around 5 to 5.5 centimeters.

The original Yellow MSX PCB have a height of around 8cm - near double the typical height.  The greater height was generally required, as I needed the extra PCB space to fit all the components for each of the various modules.

In particular, the V99x8 module is quite a challenge - the 64 PIN DIL chip takes up almost half of the PCB area of a conventional height of ~5cms.  Then when you add the RAM chips (4 of them) - well its just not physically possible.

That is, unless I reduce the RAM to just 64K (down from the 128K).  With just 64K, it is possible to fit all components onto the smaller PCB.  The lower RAM still allows the VDP to displays all the game graphic modes, just with less RAM available for paging - so some games might not work - but I think many still will.

But I still want to support the 128K of VRAM - and in fact, it would be very nice if I could extend support to the VDP's maximum of 192K VRAM.

What I ended up designing is a main board - at the 5.5cm height, with support for 64K - and an 'expansion board' that allows the module to support the full 192K.  The height is still the same, but the width is increased a bit.

Here is a picture of the new design, with the 64K RAM on a single 5.5cm PCB:

<div style="text-align:center">
  <img style="width:70%" src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-profile.jpg" alt="Green stegosaur V9958 RGB Module with 64K RAM on single 5.5cm high PCB" />
</div>

And here is it with the expansion installed:

<div style="text-align:center">
  <img style="width:70%" src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-with-192k-ram-profile.jpg" alt="Green stegosaur V9958 RGB Module with 192K RAM installed with the expansion board"  />
</div>

With the expansion board, its a tight fit - and the width of the 2 combined PCBs does extend beyond the RC2014/RCBus's typical spacing.  (If the RAM was soldered directly and not socketed it would probably fit in the BUSs' standard spacing).

I am calling this series of boards - the *Green Stegosaur Series*.  The intention is that the series will be compatible and mostly the same as the Yellow MSX series, but with the smaller height.  It will probably necessitate that some modules are split into 2 - eg the MSX Memory module will definitely need to be split into 2 seperate PCBs.  So this series will probably require more slots on the backplane.

If you are not interested in MSX, though, this new Video Module's form factory, might be a better fit for your RC2014/RCBus rigs.

I have more details of the module and schematic up on my site now: [https://www.dinoboards.com.au/stegosaur/v9958/](https://www.dinoboards.com.au/stegosaur/v9958/)

And its listed on my shop for sale as a kit [https://shop.dinoboards.com.au/product/stegosaur-msx-v9958-rgb/](https://shop.dinoboards.com.au/product/stegosaur-msx-v9958-rgb/)


