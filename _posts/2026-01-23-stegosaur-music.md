---
layout: post
title: Stegosaur MSX YM2413 Music for RC2014/RCBus
tags: stegosaur msx ym2413
---

Next module to be downsized, is the MSX YM2413 Music Module.

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/music/images/profile.jpg"><img style="width:80%" src="{{ site.baseurl }}/stegosaur/music/images/profile.jpg" alt="Assembled Profiled" width="100%"/></a>
</div>

This new module, is similar to the Yellow MSX Music kit, with some cool updates and improvements:


### Improved Sound Quality

When I started designing and developing kits for the RC2014 platform, I only had a limited knowledge of digital electronics - just enough basic knowledge and understanding to work from.  A lot of digital electronics is just 'boolean' logic and some flip-flops -- this I kind of knew -- not sure how -- I guess some of the things I did as a kid had stayed with me.

There are a lot of online tutorials, blogs, helpful forums, that made my goal of re-creating a MSX based computer, seem at least a possibility for me.

Though, as with most learning experiences, its the lack of understanding of what you don't know (those unknown unknowns), that can present some real confusing situations.  I had a few of those - and probably still have more to come!

But I also **knew**, I knew nothing about analogue circuits.  Things such as power supplies, and audio stuff - thats just some dark magic!

So when I attempted to design the MSX-MUSIC module, based on the YM2413 chip, I ended up doing a lot trail and error experimentation, to figure how to use these op-amp things, to amplify the audio signal.

The first versions worked, but had a very poor signal to noise ratio.  The digital interference of the rest of the computer would always just bleed into the sound mix.  That irritating digital noise would never quite go away.

I introduced a LC filter on the power supply (an inductor and capacitor) - this helped a lot with the digital noise.  But the op-amps stage was still far from optimal.

With this version, I have further tweaked the op-amps stage to avoid rolling off the higher frequencies, whilst also reducing the noise considerably.  In addition, it now has 2 op-amps - to enable its stereo operation.

I certainly won't be getting a job at any high end audio manufacturer - or any audio equipment manufacturer for that matter - but I can honestly say - I have designed an op-amp amplifier circuit that actually works!  Well done me.


### Pseudo Stereo Output

Like the updated GAME module, I have updated this module to support a stereo mix.  Whereas the GAME's YM2149 has 3 audio outputs that are spread into a stereo mix, the YM2413 has only 2 audio outputs: Melody (MO) and Rhythm (RO).

The new design has a partial left/right mix for these 2 signals - there is a small resistor between the 2 signals, so that its not producing a full rigid left/right separation.

The audio received from the GAME module's output (via a short 3.5mm audio connector) - is passed through and its stereo signal is maintained.  Check out the short video below, demonstrating both the MUSIC and GAME audio mixed together.

### MSX-MUSIC ROM extension split into a separate module

Due to the smaller PCB, its not possible to include the MSX-MUSIC ROM for MSX-BASIC extension.  If this module is only used in a stock RC2014/RCBUS RomWBW build, the ROM module is not required nor is it compatible.

For a full MSX configured system, the ROM module can be installed separately.

### Dropped the on-board clock

And just like I did for the Stegosaur GAME module, I dropped the on-board clock generator - and sourced the clock signal from the main bus (CLK1 or CLK2).


### Demo

<div style="text-align: center;">
<iframe width="400" height="225" src="https://www.youtube.com/embed/-CsA9YbaxGs?si=00M0EPOxEBr2tnYo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<br/>

### More details

I have more details of the module and schematic up on my site now: [https://www.dinoboards.com.au/stegosaur/music/](https://www.dinoboards.com.au/stegosaur/music/)

And its listed on my shop for sale as a kit [https://shop.dinoboards.com.au/product/stegosaur-msx-ym2413-music/](https://shop.dinoboards.com.au/product/stegosaur-msx-ym2413-music/)

And for the MSX Builds - the MSX-MUSIC ROM Module: [http://www.dinoboards.com.au//stegosaur/music-rom/](http://www.dinoboards.com.au//stegosaur/music-rom/)
