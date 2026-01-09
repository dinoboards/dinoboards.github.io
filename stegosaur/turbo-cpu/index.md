---
layout: default
title: Turbo CPU
description: Z80 CPU running at up to 20Mhz.
product_url: https://shop.dinoboards.com.au/product/stegosaur-turbo-cpu/
---

<div style="display: flex; justify-content: space-between; gap: 20px;">
  <div style="flex: 0 0 100px;">
    <img src="{{ site.baseurl }}/assets/new.png" width="100px"/>
  </div>
  <div style="flex: 3;">
    <h1>Stegosaur Turbo CPU</h1>
    <p>Code: DB303</p>
  </div>
</div>


This module is designed to replace your existing RC2014/RCBus CPU and give you the full power of a Z80 running at 20Mhz, yet still be broadly compatible with original software and your other RC2014/RCBus modules.

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/turbo-cpu/images/profile.jpg"><img style="width:80%" src="{{ site.baseurl }}/stegosaur/turbo-cpu/images/profile.jpg" alt="Assembled Profiled" width="100%"/></a>
</div>

For a system configured to run a full MSX configuration, you typically need to run your CPU at approximately 3.5Mhz, as software written for the platform at the time, would assume your system was clocked at this speed.  If you attempt to run programs at a higher cpu clock speed, you will probably get video corruption, I/O problems -- it just wont work!.

But these days, its possible to buy a brand new Zilog Z80 chip, rated at 20Mhz (Z84C0020PEG).  For me in the mid 80s, that would have been an unimaginable speed!

We achieve compatibility by applying a combination of hardware wait states (pausing the CPU for a bit) and automatically slowing the clock down to the 3.5Mhz for short periods of time when the CPU is interacting with your other modules.

A 3 way slider, soldered on the front of the module, gives you total control of the CPU speed.  Using this switch, you can at any time switch into 1 of 3 modes:

1. Full 20Mhz clock speed, with 1 wait state when accessing memory, and slows the clock to 3.5Mhz for 31 clock cycles when it accesses IO devices (SIO/2, PPI, V9958 etc).
2. Full 20Mhz clock speed as mode 1, but with 3 wait states for accessing memory.
3. Standard MSX speed 3.5Mhz CPU, M1 Wait state for accessing memory.

Despite the extra wait states and clock slow down, I have found a typical speed improvement of between 4 and 5 times faster - even for software the does lots of interactions with the V9958, you can still see a very large improvement.

Here is a demonstration of the very similar Yellow MSX Turbo CPU module, to give you an idea of the performance difference.

<div style="text-align: center;">
<iframe width="460" height="315" src="https://www.youtube.com/embed/coI_g9XZ_w4?si=EzXHP6c1SxNOmBtF" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

# Key features

* Support Z80 running at 20Mhz
* 3 way slider to select fast, medium or standard speeds
* Blinky Leds to indicate turbo mode and clock slow down states

<div class="hh1">Images</div>

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/turbo-cpu/images/parts.jpg"><img src="{{ site.baseurl }}/stegosaur/turbo-cpu/images/parts.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/turbo-cpu/images/assembled.jpg"><img src="{{ site.baseurl }}/stegosaur/turbo-cpu/images/assembled.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/turbo-cpu/images/pcb-front.jpg"><img src="{{ site.baseurl }}/stegosaur/turbo-cpu/images/pcb-front.jpg" width="90%"/></a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/turbo-cpu/images/pcb-back.jpg"><img src="{{ site.baseurl }}/stegosaur/turbo-cpu/images/pcb-back.jpg" width="90%"/></a></td>
  </tr>
</table>

# Bill of Materials

\* Self Source Reference are supplied as a guide only.  Please double check, in case of typo or errors in listing.

#### Base Kit

| Count | Name                    | Self Sourcing*                                            |
| :---: | ----------------------- | --------------------------------------------------------- |
|   5   | 0.1uF Ceramic Capacitor                  |                                                           |
|   2   | 22pF                    |                                                           |
|   1   | 47 Ω (3.4mm)            |                                                           |
|   2   | 470 Ω (3.4mm)           |                                                           |
|   1   | 10K Ω (3.4mm)           |                                                           |
|   1   | 10k Ω Bussed x 6        | Mouser: 858-L071S103LF<br/>DigiKey: 4607X-101-103LF-ND    |
|   2   | 3mm LED                 |                                                           |
|   1   | ATF22V10C               |                                                           |
|   1   | ATF16V8                 |                                                           |
|   1   | 74AC153                 |                                                           |
|   1   | 74AC74                  |                                                           |
|   1   | 74HC02                  |                                                           |
|   1   | 74HC393                 |                                                           |
|   1   | SP3T Slide Switch       | Mouser: 611-OS103011MA7QP1<br/>DigiKey: CKN9561-ND        |
|   1   | 20 Mhz Oscillator       | Mouser: 774-MXO45HS-3C-20.0<br/>DigiKey: 535-9173-5-ND    |
|   2   | Right Angle 2x20 Header | Mouser: 649-68020-140HLF<br/>DigiKey: 2057-PH2RA-40-UA-ND |
|   1   | 40 POS IC SOCKET        | Mouser: 571-1-2199299-5<br/>DigiKey: 2057-ICS-640-T-ND    |
|   1   | 24 POS IC SOCKET NARROW | Mouser: 571-1-2199298-8<br/>DigiKey: 2057-ICS-324-T-ND    |
|   1   | 20 POS IC SOCKET        | Mouser: 571-1-2199298-6<br/>DigiKey: 2057-ICS-320-T-ND    |
|   1   | 16 POS IC SOCKET        | Mouser: 571-1-2199298-4<br/>DigiKey: 2057-ICS-316-T-ND    |
|   4   | 14 POS IC SOCKET        | Mouser: 571-1-2199298-3<br/>DigiKey: 2057-ICS-314-T-ND    |
|   1   | 4 OSCILLATOR SOCKET     | Mouser: 535-1108800<br/>DigiKey: A463-ND                  |
|   1   | PCB                     |                                                           |

#### Optional 20Mhz CPU

| Count | Name      | Self Sourcing* |
| :---: | --------- | -------------- |
|   1   | Z80 20Mhz | Z84C0020PEG    |



## Compatibility

I have tested running at 20Mhz on my specific back-plane and set of modules without any problems.  But due to differences in combination and configuration of RC2014 kits - you may find with your specific situation, there are signal degradation issues at 20Mhz that may cause non-reliable operation.  You can use the 3 way slider to force the module to operator at a lower speed.

# Operation

The 3 way slider at the front of the module is used to change the timing settings of the Z80.  In its top most position, the CPU will operate at the speed as per your bus clock.

In the middle position, the processor will boost to 20Mhz, but it includes 3 WAIT states for all memory access.

In the bottom position, the processor will boost to 20Mhz, but only have 1 additional WAIT state added for any memory access.


# What else do I need to make this work?

You need a RC2014/RCBus build.  This can be configured with MSX modules or other RC2014/RCBus modules.

I have tested on a conventional RC2014 build and with the MSX Modules.

It will replace your RC2014 CPU.

Unlike the Yellow Turbo CPU Module, this module still requires an external clock source (slow-clock).  This slow clock can be generated using any RC2014/RCBus clock modules (eg: The RC2014 Dual Clock Module).  You can also use the V99x8 RGB Video modules, with their appropriate jumper settings to create a 'slow clock' signal onto the CLK1 bus lane.

# How does it work?

Running RC2014 build at higher clock speeds presents a few challenges for reliable operation. To increase the CPU clock speed of your system, a few things need to be considered:

1. What's are the frequency and rise/fall time limits for the back-plane and various modules?  Its very easy to introduce cross talk or other signal quality issues as your clock rate goes up.
2. What the timing limits for the typical RAM/ROM modules. If you try to run your Z80 at 20Mhz, will the RAM and ROM modules keep up?
3. Similarly, what's the timing limits for various I/O devices. Some chips, like the SIO/2 might be rated only to speeds around 6Mhz. It is unlikely such chips will cope with a Z80 running at 20Mhz.
4. In addition devices like the V9958 Video Display Processor have additional timing requirements - the rate of 'commands' that can be sent and executed must not exceed its capacity. If you send drawing commands to this chip too quickly, you will likely get video corruption.

All the various I/O modules and RAM/ROM modules available for RC2014 typically expect an operation frequency of between 3.5Mhz and 7Mhz. So if we increase the clock frequency of the CPU, we have to figure out a way to ensure a wide range of compatibility with all these external modules.

One of the things that work in our favour though, is despite the fact the Z80 is running at 20Mhz, it will not access I/O and memory at this rate.  This is due to the way it requires a few internal clock cycles for various operations, so the effective rate of communications to modules will be lower. For example, all I/O request take at least 4 Clock cycles to complete, and some instructions processed by the Z80 can take up to 20 clock cycles.  We have to consider the timing requirements and operation of the Z80 as described in its datasheet.

The Z80 supports the concepts of additional hardware based wait states.  By designing some logic to enable extra wait states when accessing I/O and memory devices, we can force the CPU to 'wait' or pause for additional clock cycles, thus allowing the I/O and memory chips the time they need to process the read/write requests from the CPU.

It also important to remember, that even at the 3.5Mhz clock speed, the original MSX standard required an extra wait state when reading memory during the M1 cycle.  This was required as the speed of memory, particularly ROM chips of the day, were not able to keep pace with a Z80 running at 3.5Mhz.  Although modern RAM and ROM chips are quite capable of keeping up, if we remove this wait time, original software and games may not work right.

The V9958 in particular, presents a compatibility challenge when running the Z80 at a higher clock speed.  So much original software will be optimise to send commands to the V9958, on the assumption that the CPU is running at 3.5Mhz.  Although, with my testing to date, I found the V9958 can communicate with a Z80 running at 7Mhz.  This will only work as long as our software manages the rate at which it issues commands to the V9958.  Original unaltered software, typically will cause video corruption, even at 7Mhz.

The timing requirements for the V9958 can be quite complicated.  Depending on if you are issuing a command or attempting to access the VRAM the time that's needed between 1 operation and the next can be quite confusing to figure out.  Despite this, the software authors, have optimised this to the highest possible degree.  For a detailed analysis of the timing, check this [article](http://map.grauw.nl/articles/vdp-vram-timing/vdp-timing.html) out.  Any increase in CPU speed without hardware waiting, will cause original software to not work.  But if we go with 'pausing' the CPU to achieve compatibility, running at 20Mhz, we may need to pause the CPU for 90 clock cycles (or more).

So to solve this problem, instead of 'pausing' the CPU, I went for a different approach.  When I/O interactions are undertaken by the Z80, the Z80's clock is switched from the 20Mhz rate, down to the standard 3.5Mhz. The CPU is feed this slow clock for 31 clock cycles (at 3.5Mz), after which it revert the clock back to the full 20Mhz.  I found that about 30 odd cycles was enough to achieve general compatibility.

The clock signal supplied to the CLK1 RC2014/RCBus bus is typically independent of the clock signal sent to the CPU.  When the CPU is operating at the full 20Mhz, the CLK1 signal, will continue at its selected rate.  So other modules that use this clock signal, such at the SIO/2, and will not see any difference in clock signals.


# PLD Code

This module has 2 (Programable Logic Devices) PLD chips to manage the clock slow down and cpu wait states.

The ATF22V10 is responsible for initiating and holding the clock braking, upon any I/O operation.

The ATF16V8 is responsible for issuing any additional WAIT states to the CPU.

* <a target="_newwindow" href="https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/msx/turbo-cpu.pld" target="_blank">msx/turbo-cpu.pld</a>
* <a target="_newwindow"  href="https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/msx/turbo-cpu-mwait.pld" target="_blank">msx/turbo-cpu-mwait.pld</a>

The 3 way slider's state is sent to these 2 chips to allow the user to select 2 turbo modes or a turbo off mode.





# Schematic

* <a target="_newwindow" href="./schematic-1.1.pdf">Schematic (revision 1.1)</a>

# Key difference with Yellow Turbo CPU

| Description                | Yellow MSX Version                                         | Green Stegosaur Version          |
| -------------------------- | ---------------------------------------------------------- | -------------------------------- |
| Turbo Clock                | On board 20Mhz                                             | On board 20Mhz                   |
| Slow Clock (CLK1)          | On board with selectable rates from 0.3072Mhz to 7.3728Mhz | **Requires external slow clock** |
| Clock (CLK2)               | On board with selectable rates from 0.3072Mhz to 7.3728Mhz | None                             |
| External Slow Clock Source | Optional via jumpers                                       | Required                         |
| Power On Reset | None | Enabled from version 1.1 and above |
| PCB Height                 | 8.0 cm                                                     | 5.5 cm                           |
| Colour                     | Yellow                                                     | Green                            |

# Assembly Guide

{% include soldering-order.md %}

#### NOTE 1 - Oscillator installation

Please pay careful attention when you insert the oscillator into the DIP socket (or directly in the PCB), to its orientation.  If you get this wrong, you will almost certainly destroy the oscillator.  You may guess how I found this out!

#### NOTE 2 - 10k Ω Bussed resistor

The bussed resistor must be oriented correctly.  The side with markings must face toward the Z80 processor.

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/turbo-cpu/images/bus-resistor-orientation.jpg"><img src="{{ site.baseurl }}/stegosaur/turbo-cpu/images/bus-resistor-orientation.jpg" width="45%"/></a>
</div>

{% include disclaimer.md %}
