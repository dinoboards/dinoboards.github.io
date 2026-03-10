---
layout: post
title: New boards under development
tags: msx rc2014
---


The latest iterations of Video, Game(sound), Memory and Keyboard modules have matured quite well - and with them now selling on Tindie for a while, I have now been able to spend a bit of time on developing some more MSX boards.

## RTC

The rtc module was the first board I had started with - but I paused it to focus on the others, as it was not required to be able to boot up in MSX BIOS/DOS.  I have since gone back to this module.

After a few attempts getting the timing right, I now seem to have something that keep fairly accurate time.  I also added to the board, support for the MSX F4 port.  The F4 port enables MSX BIOS to know if its doing a cold boot or a warm boot.  It's basically just one bit that is reset on power, but not on reset.

I have a new PCB arriving soon that includes the F4 - ready for assembling and testing.

## FM-MUSIC

This one is the most experimental for me.  The MSX-MUSIC system is based on the YM2413 sound chip.  There seems to be a few variations of implementation - again msx.org is a great source of information -> [https://www.msx.org/wiki/MSX-MUSIC](https://www.msx.org/wiki/MSX-MUSIC)

And this project [https://github.com/RBSC/F4-FMPAC](https://github.com/RBSC/F4-FMPAC) is giving me a lot of clues.

I am learning a lot about op-amps - will see if I can figure this all out.

## Cartridge slots

I also designing a new backplane that provides MSX cartridge slots - although i am a little unsure how i am going to test this - i need to actually source some cartridges that don't cost an arm and a leg!

