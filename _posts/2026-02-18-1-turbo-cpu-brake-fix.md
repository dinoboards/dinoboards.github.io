---
layout: post
title: Fixing the fix to Turbo CPU's BRAKE
tags: Z80 TURBO MSX RC2014 RCBUS
---

Well.  Perhaps readers of this blog, should ignore my previous posting.  It seems I got a fundamental bit of logic wrong.  What I thought was a failure of the BRAKE Generator to slow down the CPU upon an IORQ request, was not an entirely correct analysis of the situation.

The IORQ signal goes active (low) in three scenarios:

1. IORQ and RD - CPU is reading from an I/O device
2. IORQ and WR - CPU is writing to an I/O device
3. IORQ and M1 - CPU is executing its interrupt acknowledge cycle

I had completely missed the potential for the 3rd scenario.

Now, I only run my Z80 in Interrupt Mode 1 (IM1), as per MSX.  I don't have any RC2014/RCBus modules that work or are designed for Interrupt Mode 2 (IM2).  In IM2 mode, devices place a vector byte on the data bus during the INT ACK cycle.  In IM1, the CPU still conducts the Int Ack cycle - and just ignores the sample byte.

So to summarise, what my logic was originally doing was enabling the clock slow down for IORQ read & write operations correctly, and needlessly stretching the clock for one cycle during an INT ACK phase.

So I have 'reverted' the PLD code to not trigger the slow down during the Int Ack cycle - but I did stop it from 'stretching' the clock during the Int Ack cycle.




