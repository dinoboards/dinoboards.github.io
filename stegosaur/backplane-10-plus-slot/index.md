---
layout: default
title: Stegosaur 10 + MSX Slot Backplane
description: A RCBus 80 way backplane and single MSX Game Cartridge Slot
product_url: https://shop.dinoboards.com.au/product/stegosaur-10-rcbus-msx-slot-backplane/
---


<div style="display: flex; justify-content: space-between; gap: 20px;">
  <div style="flex: 0 0 100px;">
    <img src="{{ site.baseurl }}/assets/new.png" width="100px"/>
  </div>
  <div style="flex: 3;">
    <h1>Stegosaur 10 + MSX Slot Backplane</h1>
    <p>Code: DB312</p>
  </div>
</div>


A 10 slot RCBus 80 way backplane plus a single MSX 50 way cartridge edge connector.

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/profile.jpg"><img style="width:70%" src="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/profile.jpg" alt="Assembled Profiled" width="100%"/></a>
</div>

The backplane is an alternative to the <a href="/backplane">Yellow MSX 12+1 Backplane</a> and the optional <a href="/slot-extension">MSX (Dual) Cartridge Extension</a>.

With enough slots to fit the Stegosaur MSX+ modules, with a single plus one RC2014/RCBus spare slot.  The spare can be used for the Green USB Module.  If more modules capacity is desired, please consider the Yellow MSX 12+1 Backplane.

# Key features

* 10 RC2014/RCBus 80 way slots
* A single 50 way edge MSX Cartridge slot
* An optional on-board 5V DC converter
* Reset switch
* 4 way power terminal block for easy extension or alternative powering
* Optional direct 5V in via DC barrel connector

<div class="hh1">Images</div>

<table>
  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/pcb-front.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/pcb-front.jpg" width="90%"/><br/>PCB (V1.0) Front</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/pcb-back.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/pcb-back.jpg" width="90%"/><br/>PCB (V1.0) Back</a></td>
  </tr>

  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/pcb-1.1-front.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/pcb-1.1-front.jpg" width="90%"/><br/>PCB (V1.1) Front</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/pcb-1.1-back.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/pcb-1.1-back.jpg" width="90%"/><br/>PCB (V1.1) Back</a></td>
  </tr>

  <tr>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/backplane-1.1-installed.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/backplane-1.1-installed.jpg" width="90%"/><br/>PCB (V1.1) Assembled</a></td>
    <td width="50%"><a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/parts.jpg"><img src="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/parts.jpg" width="90%"/><br/>Main Parts</a></td>
  </tr>

</table>

# Revisions

## V1.0

First release

## V1.1

The PCBs width has been extended and the cartridge slot spaced a bit further away from slot 10.  This enables the installation of the wide V9958 Module with its expansion RAM to fit comfortably.  The image below show the V1.1 backplane fully stacked with all the Stegosaur modules and the Green USB for RC module.

<div style="text-align: center;">
<a target="_newwindow" href="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/backplane-1.1-profile-installed.jpg"><img style="width:65%" src="{{ site.baseurl }}/stegosaur/backplane-10-plus-slot/images/backplane-1.1-profile-installed.jpg" alt="Assembled Profiled" /></a>
</div>
<br/>

# Bill of Materials

\* Self Source Reference are supplied as a guide only.  Please double check, in case of typo or errors in listing.

#### Base Kit

| Count | Name                       | Self Sourcing*                                         |
| :---: | -------------------------- | ------------------------------------------------------ |
|  20   | 40 Way SIL Socket*         |                                                        |
|  12   | 0.1uF Ceramic Capacitors   | Mouser: 594-K104K10X7RF53L2<br/>DigiKey: BC5137-ND     |
|   1   | 2.1mm Power Jack           | Mouser: 490-PJ-002B<br/>DigiKey: CP-002B-ND            |
|   1   | Tactile Switch             | Mouser: 506-FSM4JH<br/>DigiKey: CP-002B-ND             |
|   1   | SPDT Toggle Switch         | Mouser: 612-200MSP1T1B2M6QE                            |
|   1   | 4 Way Screw Terminal       | Mouser: 179-TB0010-500-02GR                            |
|   2   | 470 Ω (3.4mm)              |                                                        |
|   2   | 3mm LEDs                   |                                                        |
|   1   | ATF16V8B-15PU              | Mouser: 556-AF16V8B15PU<br/>DigiKey:	ATF16V8B-15PU-ND  |
|   1   | 20 POS IC SOCKET           | Mouser: 571-1-2199298-6<br/>DigiKey: 2057-ICS-320-T-ND |
|   1   | 50 Pin Card Edge Connector | Mouser: 571-5530841-5<br/>DigiKey: 5530841-5-ND        |

#### Optional 5V Converter

| Count | Name                           | Self Sourcing*                                                                                                         |
| :---: | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
|   1   | Optional ~12V to 5DC Converter | Mouser: 919-R-78K5.0-2.0L<br/>DigiKey: 945-R-78K5.0-2.0L-ND<br/>~~Mouser: 946-MEZD71202A-G<br/>DigiKey: 1589-1465-ND~~ |

#### Optional 12V Converter

| Count | Name                              | Self Sourcing*                                                                |
| :---: | --------------------------------- | ----------------------------------------------------------------------------- |
|   1   | Optional 5V to +/-12VDC Converter | Mouser: 709-DPU01L-12<br/>~~DigiKey: 1866-1408-ND~~<br/>DigiKey: 1951-3433-ND |

# What's included?

The full kits includes everything you need (PCB, capacitors, IC sockets, connectors, and the ICs).

The ATF16V8B-15PU PLD is supplied flashed.

Please note that mounting stand-offs are not supplied.

# What else do I need?

This backplane requires modules.  Any compatible RC2014/RCBus module can operate on this backplane.

The MSX Cartridge slot will only work if you have the required set of MSX modules.  It is not compatible with RomWBW.


# Operation

### Main power supply

This backplane works much like many other RC2014/RCBus backplanes.  Provide an input voltage that is appropriate for the installed 5VDC Converter (typically 12V).  Note the polarity of the power supply connector - the inner pin of the DC Barrel Connector is positive and the outer shield is ground.

The 5V optionally supplied is rated at 5V @ 2 Amps.

### Optional +12V/-12V

The optional +12V/-12V connector is only required for MSX Cartridges that require these voltages - most cartridges do not.

I have not been able to test this with real cartridges.

### Cartridge Compatibility

There is no physical keying of the cartridges.  Inserting a cartridge the wrong way may result in damage to platform and or cartridge.

Cartridges need to face outwards to the right.

Please use the cartridge with caution.  Double check voltages and signals before risking an original MSX Game Cartridge.  I have tested on a number of MSX1 and MSX2 cartridges with success - and many builders have reported good compliance.  Use is at your own risk.

# Schematic

* <a  target="_newwindow" href="./schematic.pdf">Schematic</a>

# Key difference with Yellow MSX 12+1 Backplane

| Description         | Yellow MSX Version                      | Green Stegosaur Version    |
| ------------------- | --------------------------------------- | -------------------------- |
| MSX Cartridge Slots | 2 with optional extension module        | 1 single only on backplane |
| RC2014/RCBus Slots  | 12 (1 reserved for Cartridge Extension) | 10                         |
| Colour              | Yellow                                  | Green                      |

# Assembly Guide

### General guidelines

#### Soldering item order

Generally, you want to solder items from lowest height to largest height.  Review the components you need to solder, and note their progressive heights.

1. Resistors
2. Ceramic capacitors
3. LEDs
4. Reset Switch
5. IC Socket
6. Power Switch
7. Main SIP Headers
8. 5V DC Converter
9. DC Barrel Connector
10. 50 Way Edge Connector

### Specific Notes

Please note the following specific points regarding this module:


#### NOTE 1 Socket Headers

There are a lot of headers.  Pay close attention to their alignment, ensure square and flush with each other.  Keep the colours coordinated and consistent.  I choose black SIP for the left side and the coloured SIP for the right side.

#### NOTE 2 Capacitors for 5VDC converter

Capacitors C10 and C11 are typically not required. Footprint is provided if additional DC filter required/desired.

#### NOTE 3 Bypassing the 5VDC converter

You can choose to power your backplane with a direct 5V power supply.

For bypassing, do not install the on-board converter and short the 5V Direct jumper and supply a good 5V power to the barrel or via the 4 way terminal block.  You typically needs at least 1 to 1.5 Amp.  2 Amp is recommended.

#### NOTE 4 Cartridge Slot

Please use the cartridge with caution.  Double check voltages and signals before risking an original MSX Game Cartridge.  I have tested on a number of MSX1 and MSX2 cartridges with success - and many builders have reported good compliance (with the equivalent Yellow MSX Backplane).  Use is at your own risk.


#### NOTE 5 +12/-12V power

The optional onboard +12/-12 power supply is optional, and only required for specific cartridges that need these extra voltages.  It is safe to use without the +-12V supply.

{% include disclaimer.md %}

