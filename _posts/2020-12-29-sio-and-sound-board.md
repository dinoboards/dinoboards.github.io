---
layout: post
title:  "SIO and Sound Board"
tags: msx rc2014
---

<p><strong>RC2014 SIO/2</strong></p>

<p>Managed to get the RC2014 SIO/2 Board to work with my MSX rig.</p>

<p>Its took a bit of finessing to get the higher baud rate (57200) working with MSX BIOS interrupt handler - the overheads make it easy to lose data.&nbsp;</p>

<p>The application talks directly to the SIO chip.&nbsp; &nbsp;A future goal will be to integrate the serial driver within the BIOS/Nextor systems.</p>

<p><strong>Sound/Controller Board</strong></p>

<p>After a few bodge fixes - i was able to get the sound board working (YM2149 chip).&nbsp; I considered using the&nbsp;<a href="https://www.tindie.com/products/semachthemonkey/ym2149-sound-card-for-rc2014-retro-computer/">RC2014 Sound board</a>, but I don't think the revision I have supports the MSX ports.&nbsp; A later revision seems to.&nbsp;&nbsp;</p>

<p>The board I designed, also support controller ports -- if only I owned a MSX controller!</p>

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/8841311609210338762.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/8841311609210338762.jpg" width="75%"/></a>
</div>


<p>(The missing chips are required for the controller ports - will install when i get an MSX controller to test with)</p>

<p>In the next few days, I will try and get myself organised, and upload designs.</p>

<p>In the meantime you can watch me playing PACMAN really badly.</p>

<div class="video-container"><iframe style="width: 500px; height: 281px;" src="//www.youtube.com/embed/PlqrQ548rpE" frameborder="0" allowfullscreen=""></iframe></div>
