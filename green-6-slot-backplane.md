---
layout: default
title: 6 Slot Backplane
description: 6 Slot Green Backplane
tindie_product_url: https://www.tindie.com/products/dinotron/6-slot-green-rcbus-backplane/
github_url: https://github.com/dinoboards/ez80-for-rc
coming_lectronz_product_url: https://lectronz.com/products/
is_new: true
---

# 6 Slot Green Backplane <img src="{{ site.baseurl }}/assets/new.png" style="width:36px; margin-left: 8px; position:absolute"/>

<div style="text-align: center;">
  <img src="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-assembled-profile.jpg" width="70%"/>
</div>

A standard 80-way RCBus/RC2014 compatible backplane.

Suitable for the Green Machine Series of kits.

# Key features

* Onboard 5V DC converter
* Onboard switch and power-on LED
* Onboard system reset switch
* Single ground plane for maximum signal integrity
* Optional bypass support for direct 5V powering
* Screw terminal for external 5V output
* RCBus and RC2014 compatibility

## What is the Green Machine Series of Retro Kits

The Green Machine Series of kits are designed around the RCBus/RC2014 bus, powered by an eZ80 CPU (as apposed to the Z80 CPU), and are broadly compatible with many RC2014 and RCBus kits and CP/M and RomWBW software stacks.

For more information of the eZ80 CPU, see the [eZ80 CPU kit](/ez80-for-rc).

## FAQ

<table><tr>
<td>Can I use other backplanes - do I have to use this one for an eZ80 build?</td>

<td>You can use any RCBus compatible backplane that supports all 80 bus lines.  You can even use non-green ones!  Just make sure it has the full 80 lanes (2x40 pin headers)</td>
</tr></table>

# Images

<table>
  <tr>
    <td width="50%"><a href="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-top.jpg"><img src="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-top.jpg" width="90%"/></a></td>
    <td width="50%"><a href="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-bottom.jpg"><img src="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-bottom.jpg" width="90%"/></a></td>
  </tr>
  <tr>
    <td width="30%"><a href="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-assembled.jpg"><img src="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-assembled.jpg" width="90%"/></a></td>
    <td width="70%"><a href="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-assembled-profile.jpg"><img src="{{ site.baseurl }}/assets/green-6-slot-backplane/pcb-assembled-profile.jpg" width="90%"/></a></td>
  </tr>

  <tr>
    <td colspan="2" style="text-align: center;" ><a href="{{ site.baseurl }}/assets/green-6-slot-backplane/6slot-parts.jpg"><img src="{{ site.baseurl }}/assets/green-6-slot-backplane/6slot-parts.jpg" width="45%"/></a></td>
  </tr>

</table>

# Bill of Materials

The following items will be included in your kit.

|Count   | Name  | Detail  | Vendor Link* |
|:------:|-------| ------- | ---- |
| 4      |  0.1uF | Multilayer Ceramic Capacitors MLCC 2.54mm | [mouser](https://au.mouser.com/ProductDetail/594-K104K15X7RF5UL2) |
| 12     | 1x40 header socket (green & black) | 2.54mm spacing | EBAY SEARCH: 40Pin Female Single Row Header Strip |
| 1      | 3mm GREEN LED | Conventional 3mm LED | |
| 1      | 1	470 Ω | 3.4mm width | |
| 1      | DC Barrel Connector | Same Sky: PJ-002B (2.5mm/6.5mm) | [mouser](https://au.mouser.com/ProductDetail/490-PJ-002B) |
| 1      | Tactile Switch | 5.99mm | [mouser](https://au.mouser.com/ProductDetail/506-FSM4JH) |
| 1	     | Power Terminal Block (2POS) | | [mouser](https://au.mouser.com/ProductDetail/179-TB0010-500-02GR) |
| 1	     | SPDT Toggle Switch | E-Switch: 200MSP1T1B2M6QE | [mouser](https://au.mouser.com/ProductDetail/612-200MSP1T1B2M6QE)
| 1      | Compatible DC Converter 12V to 5V (2amp) | MPS: MEZD71202A-G LM7805 Compatible* | [element14-aus](https://au.element14.com/monolithic-power-systems-mps/mezd71202a-g/dc-dc-converter-5v-2a/dp/3346295)
| 1      | 2 Layer PCB

\* Vendor links are supplied for reference only.  Specific product may vary, vendor may change its offering and/or components may cease production.

# Resources

* Schematic: [schematic](assets/green-6-slot-backplane/schematic.pdf)

{% include disclaimer.md %}
