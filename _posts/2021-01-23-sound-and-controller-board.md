---
layout: post
title:  "Sound & Controller Board"
tags: msx rc2014
---

<p>Just completed the build for the game board.&nbsp; This board is based on the YM2149 audio chip - with integrated game controller ports.</p>

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/3890731611445173097.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/3890731611445173097.jpg" width="75%"/></a>
</div>


<p>Its ports are configured as per the MSX specification.&nbsp;&nbsp;</p>


<p>The AY-3-8910 chip could also have been used, but to keep thing simple, i just locked in the YM2149 chip.&nbsp; They apparently have subtle sound quality differences with the major differencing being the Ym2149 has an onboard clock divider.<br></p>


<p>The board also supports mixing in other external audio signals -- in anticipation for full MSX capability.</p>


<p>The demo below is with my port of Octo/chip8 games running on a stock rc2014 build.<br></p>


<p>(I have not tested it under the MSX configuration yet)</p>


<div class="video-container"><iframe width="500" height="281" src="//www.youtube.com/embed/dUCEZpBlxgY" frameborder="0" allowfullscreen=""></iframe></div>


<p>The Chip8/Octo port project is at:&nbsp;<a href="https://github.com/dinoboards/rc2014-chip8">https://github.com/dinoboards/rc2014-chip8</a>&nbsp;(It's not fully implementing all the octo instructions yet)</p>


<p>More details of Chip8/Octo can be found at: <a href="https://github.com/JohnEarnest/Octo">https://github.com/JohnEarnest/Octo</a></p>


<p>Game controller board project page:&nbsp;<a href="https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/game">https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/game</a>&nbsp;(includes schematic)</p>

<p>And shoutout for the controller from:&nbsp;<a href="http://retrogameboyz.com">http://retrogameboyz.com</a></p>
