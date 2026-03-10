---
layout: post
title: Integrating the RC2014 WIFI Module
tags: msx rc2014
---

Over the last couple of weekends I have manage to get the [RC2014 ESP8266 WIFI Module](https://z80kits.com/shop/esp8266-wifi-module/) working in MSX-DOS.

I now have a 'WIFI' modem integrated into the serial communication.  Finally, my RC2014 no longer needs to be 'connected' to my main PC - it can reach out through the Internet all on its own.

I have been writing my own custom firmware for ESP8266 to give the MSX/RC2014 kit all it needs.

At the moment, I can:

* Use my terminal emulator application (formally called telnet) term.com to send commands to the ESP8266 module - initiate telnet connection and then access any online BBS.
* xrecv.com can now, with an optional command, receive a file from my main PC wirelessly (using xmodem over TCP/IP)

I needed to modify the WIFI Module to allow hardware flow control - otherwise the ESP8266 will overwhelm the RC2014's receive buffer.  This required adding a couple of resistors to map the 5V RTS from the SIO/2 to the 3.3V CTS/GPIO13 line.  Flow control is only needed in the one direction - from ESP8266 to SIO/2.  When transmitting from the SIO/2 to the ESP8266, the ESP8266 will easily keep up at the 19200 baud rate.

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/4896721631404851312.png"><img style="" src="{{ site.baseurl }}/assets/posts/4896721631404851312.png" width="45%"/></a>
</div>


The RC2014 WIFI module provides a great prototyping area to make this modification so easy:

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/2993031631405721000.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/2993031631405721000.jpg" width="75%"/></a>
</div>

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/1423301631405742428.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/1423301631405742428.jpg" width="75%"/></a>
</div>

<div style="text-align:center">
<a target="_newwindow" href="{{ site.baseurl }}/assets/posts/8289031631405780113.jpg"><img style="" src="{{ site.baseurl }}/assets/posts/8289031631405780113.jpg" width="75%"/></a>
</div>

I have never used an ESP8266 before, so had to learn a few things - I used the [Arduino Core](https://github.com/esp8266/Arduino) library - making it very easy for me to code for the chip.

But I did struggle with a few things:

1. The RX line needs to be open drain - if the internal pull up resistor is active, then the on-board voltage divider of the WIFI module will not work.  The Arduino Core, by default, enables the internal pull up - and there seems to be no interface to change this.
2. Arduino Core also does not have any functions to flip the ESP8266 into using hardware flow control for the serial lines.
I solves these problems by directly manipulating the relevant ESP8266 registers.

To disable the internal pull up resister of the RX line:

```
void setRXOpenDrain() {
  GPC(RX_PIN) = (GPC(RX_PIN) & (0xF << GPCI)); // SOURCE(GPIO) | DRIVER(NORMAL) | INT_TYPE(UNCHANGED) | WAKEUP_ENABLE(DISABLED)
  GPEC = (1 << RX_PIN);                        // Disable
  GPF(RX_PIN) = GPFFS(GPFFS_BUS(RX_PIN));      // Set mode to BUS (RX0, TX0, TX1, SPI, HSPI or CLK depending in the pin)
}
```

And for flipping hardware flow control on and off:

```
void setCTSFlowControlOn() {
 pinMode(CTSPin, FUNCTION_4); // make pin U0CTS
 U0C0 |= (1 << UCTXHFE); // Set bit to activate Hardware flow control
}

void setCTSFlowControlOff() {
 pinMode(CTSPin, FUNCTION_4); // make pin U0CTS
 U0C0 &= ~(1 << UCTXHFE); // Reset bit to deactivate hardware flow control
}
```

The full code for the ESP8266 can be found at: [https://github.com/dinoboards/yellow-msx-esp8266-wifi-module](https://github.com/dinoboards/yellow-msx-esp8266-wifi-module)

And an xmodem serial and TCP/IP client I wrote in nodejs can be found at: [https://github.com/vipoo/xmodem-cli](https://github.com/vipoo/xmodem-cli)

And the main project is still at: [https://github.com/dinoboards/yellow-msx-series-for-rc2014](https://github.com/dinoboards/yellow-msx-series-for-rc2014)
