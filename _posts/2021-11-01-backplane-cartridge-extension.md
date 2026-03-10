---
layout: post
title: Backplane and Cartridge Extension
tags: msx rc2014
---

One of the developments that been wanting for time, is the development of a custom backplane and cartridge extension.

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/9194521635807700451.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/9194521635807700451.jpg" width="75%"/></a>
</div>

In the picture above, you can see the 13 slot backplane, where the 13th slot connects to the Cartridge slot exertion board, with a custom built cartridge (flashed with pacman).

The backplane extension provides 2 buffered MSX cartridge slots.

<div style="text-align:center" class="video-container"><iframe style="width: 500px; height: 281px;" src="//www.youtube.com/embed/JcZXhmn0-9o" frameborder="0" allowfullscreen=""></iframe></div>

Now in this configuration, all seems to work - but I have not been able to test with an original cartridge - so its very possible I have a compatibility issue, that I don't understand/failed to implement correctly.

I have some original cartridges coming from Japan and Europe - and also a couple of modern cartridges coming the [msxcartridgeshop](https://www.msxcartridgeshop.com/)

So until they arrive - I can not have any confidence that implementation does not have some compatibility issue.

The main backplane has the full 80 lines (2x40) bus lanes, and avoids the need to use jumper wires between some of the modules when using the standard backplane.  It also have a bunch of LEDs between each slots, giving the whole kit a nice soft glow when powered on!
