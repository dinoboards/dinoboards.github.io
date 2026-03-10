---
layout: post
title: Serial Drivers and BBS
tags: msx rc2014
---


<p>Between ZORK play sessions, I have been working on implementing compatible serial drivers for MSX BIOS and MSX-DOS.</p>

<p>No easy task.</p>

<p>For serial communication, the only software I have developed to date, is a little utility called <em>xrecv</em>, that talks directly to the SIO/2 chip to enable simple xmodem receiving of files.&nbsp; I really want to access other serial based applications for the platform.&nbsp; For that I need to implement serial driver for the standard <a href="https://www.tindie.com/products/semachthemonkey/sio2-dual-serial-module-for-rc2014/" target="_blank">RC2014 SIO/2 Module</a>.</p>

<p>So I have been researching how MSX handled serial communications - and it seems like many computers of the era - the software support was a bit muddled.&nbsp;</p>


<p>As I did not grow up with MSX - I can only rely on online archived docs, and guess at a few things.</p>


<p>There is an official bios interface for RS232 communications for the MSX platform - integrated through the MSX Extended Bios protocol.&nbsp; This interface does seem to solve the problem of accessing interrupt driven serial devices, without knowledge of the specific hardware. (A feature missing in early IBM-PCs).&nbsp; According the msx.org's page (<a href="https://www.msx.org/wiki/Category:RS-232C_Interfaces">https://www.msx.org/wiki/Category:RS-232C_Interfaces</a>), there were quite a few products supporting this interface.&nbsp; But I struggled to find application software I could use to test against.&nbsp; This interface also seem to have performance issues - limiting to just 19200 baud.</p>


<p>What seems like a more popular driver model, are the Fossil drivers - developed by Erik Mass (<a href="https://www.msx.org/wiki/Fossil_driver">https://www.msx.org/wiki/Fossil_driver</a>).&nbsp; I&nbsp; assume (I could be wrong), this is inspired by the fossil drivers of the FidoBBS days (<a href="https://en.wikipedia.org/wiki/FOSSIL">https://en.wikipedia.org/wiki/FOSSIL</a>).&nbsp; The interface protocol for MS-DOS and MSX-DOS are quite different.</p>


<p>Anyway, armed with this knowledge, I set a goal of writing both a <em>MSX RS232 Extended Bios</em> driver and a <em>Fossil</em> driver for my RC2014's SIO/2 Module.&nbsp;&nbsp;</p>

<p>I had found some basic specification documents for the interfaces, detailing the API protocols.&nbsp; But that alone will not be enough to ensure I have developed the drivers correctly.&nbsp; &nbsp;The only way I can really verify compliance, it by testing with some applications.</p>


<p>Writing the drivers is proving to be quite an effort of endurance.&nbsp; Getting the interface worked out, ensuring the interrupt handling is functioning correctly - resolving many strange and bewildering bugs.&nbsp; But despite the hardships, I have, just today, been able to run a telnet application on my MSX machine talking to internet based BBS (using my PC as serial &lt;-&gt; internet gateway).</p>

<p><strong>The slow text based screen drawing of the BBS pages were strangely thrilling to see.&nbsp; The joy you can experience as you wonder what new image or content is slowly forming on your screen</strong><em>.&nbsp; <em>So different to the modern Web, where it usually a battle of trying to read your content as ads appear and content shuffles around.</em></em></p>

<table><tbody><tr><td>
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/4549161624756705552.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/4549161624756705552.jpg" width="30%"/></a>

<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/5273071624756824801.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/5273071624756824801.jpg" width="30%"/></a>
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/3179421624756911269.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/3179421624756911269.jpg" width="30%"/></a>

</td></tr></tbody></table>

<p>The drivers are only partially implemented - the telnet app is crashing at odd times - but as you can see from the pics above, communication is starting to happen.<br></p>

<p>I think its a few more weekends, before I could say they are at least stable - hopefully then, I can post here its all working.</p>
