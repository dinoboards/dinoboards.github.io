---
layout: post
title: Wifi Module update
tags: msx rc2014
---

Over the last few weeks, I have been mostly working on the software interface for the RC2014 Wifi module.

We now can download files from the internet directly to the CompactFlash, have the RTC modules time sync to the internet time, create telnet sessions to internet based BBS and a few other integration.

The software needs some general tiding up and testing - but for the most part seems to work well.

It consists of custom firmware in the ESP8266 module and a couple of MSX applications to interface with it.

**term.com** - a simple terminal emulator for connecting to the ESP8266 and BBS telnet sessions.

**esp8266.com** - a general purpose utility to conduct a number of functions:

**esp8266 set-wifi** - configure the wifi credentials for the ESP8266 to use

**esp8266 time-sync** - sync the RTC module with internet time

**esp8266 set-timezone** - set the time zone to use for the time syncing

**esp8266 wget** - retrieve a file from the web

A longer term goal is to create a proper MSX compatible UNAPI network driver.

All the software builds and source can be found on the github project's page:  [https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/msx](https://github.com/dinoboards/yellow-msx-series-for-rc2014/tree/main/msx) (in the apps directory)

And the custom firmware for the ESP8266 is at: [https://github.com/dinoboards/yellow-msx-esp8266-wifi-module](https://github.com/dinoboards/yellow-msx-esp8266-wifi-module)
