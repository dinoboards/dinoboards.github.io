---
layout: post
title: Possible issue with V9958
tags: msx rc2014
---

Just received a report of an issue with the Video board - in particular the address selection logic.

I have not personally experienced the fault myself, despite building a few version of the module -- but that doesn't mean much.

I have created a github issue with specific details to track the issue, copied below:

----------------

[https://github.com/dinoboards/yellow-msx-series-for-rc2014/issues/1](https://github.com/dinoboards/yellow-msx-series-for-rc2014/issues/1)

At least one person has reported an issue with V9958 Video board not working. They identified an issue with the address selection logic - in particular the diode based OR gates.

I chose to use diode base gates to reduce the chip count, but they can have issues with the fall time - which in this specific case, resulted in a board that would not work. (I have built a few iterations of the board, and never observed the issue myself, but really doesn't mean much!)

There were 2 fixes that each individually would resolve the fault:

Change the 74HCT138 to 74ACT138 , or
replace the 10K pull down resistor to a lower value - about 3.3K.
I have uploaded a pic to highlight the resistor that needed to be changed. [PCB image](https://github.com/dinoboards/yellow-msx-series-for-rc2014/blob/main/video/pictures/pcb-fix_LI.jpg)

If be great to hear if anyone else has experienced this issue.

