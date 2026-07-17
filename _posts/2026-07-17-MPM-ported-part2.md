---
layout: post
title: MP/M 2.1 running on the eZ80 Part 2
tags: eZ80 Green RC2014 RCBUS CPM

---

## Concurrent Processing Working

I have made some more progress on porting Digital Research's MP/M II Operating
System to the eZ80 for RC platform.  After fixing a few obscure bugs in my code
\- including some very challenging stack corruptions and interrupt handling
issues - I have managed to get the system stable and running two active
consoles, each with an individual, isolated process.  Multi-tasking 1980s style!

To get two consoles active, well... I needed a second console. Rather than
trying to hook up the eZ80's second UART to my PC, I just leveraged the existing
CP/M driver for CRT operation. The CRT is implemented using the *HDMI for RC*
and *USB for RC* modules (HDMI and USB keyboard).

To test whether concurrent process operation works, I decided to use a Conway's
Game of Life program. I imported a copy of Conway's Game of Life code into my
repo from
[https://github.com/kevinboone/cpmlife](https://github.com/kevinboone/cpmlife).
I needed to tweak the code a little to fix an issue with compiling under Z88DK
using the CP/M target.

I can now run two versions of LIFE on my eZ80 ...... but  very, very slowly.
This is due to the way I had to implement simulated bank switching for my custom
 MP/M BIOS (see my previous post).

## Intel to Zilog

One idea I would like to explore is taking full advantage of the eZ80's beyond
64K memory addressing capabilities. If I can get the code to avoid the need to
bank switch - or at least avoid the need to copy the upper pages of memory as it
transitions from one 64K address space to another - I can potentially fix the
extremely slow operation when running multiple processes, and probably also
increase the TPA address space for each application.

Before I can contemplate making any adjustments to the original Digital Research
code, I need to:

1. Convert the code from Intel mnemonics to Zilog Z80 mnemonics.
2. Update the compiler toolchain to use an assembler that can target the eZ80
   CPU (The GNU Assembler for eZ80).

> The Zilog Z80 is fully compatible with the Intel 8080 CPU - at least the
binary machine code is.  The two companies used very different mnemonics to
represent the same instruction. For example, the Intel representation of the
instruction `MVI A, 23H` is represented by Zilog as `LD A, 23H`.  The Z80 also
has additional instructions, and the eZ80 has even more!

Once I have the Operating System assembled using an eZ80 assembler, I can start
to modify the code and use the CPU's various extended instructions to take full
advantage of its addressing model.

I wasn't going to convert the source by hand; I needed a tool to do it. I
managed to find a tool written a long time ago to perform the code conversions,
simply called **IZ** (available at
[cpmarchives.classiccmp.org](http://cpmarchives.classiccmp.org/cpm/mirrors/www.triton.vg/TesseractRCPM+Catalog.html)).
It was originally written in Pascal in the early 1980s by John Hastwell-Batten,
and later updated and ported to C by Jon Saxton in 2010. I had to apply a couple
of additional fixes.

I compiled the code using gcc and started converting.

After converting each of the original MP/M source files, I verified that the Zilog
equivalent files produced the same binary output. When all were done, and I
again verified that the final binary image was identical, I knew the
conversion had completed successfully.


## New Build Process

Digital Research enabled users to customize the Operating System by using a tool
they supplied called `GENSYS.COM`. This tool enabled you to 'repackage' your
operating system, adjusting various settings such as the maximum number of users
and files, and defining various memory locations and buffer sizes. It would read
in a set of supplied `.SPR` files, including your custom hardware BIOS
implementation, and then prompt you for your system preferences. Once that was
done, it would relocate the binary image, updating various jump tables, and
produce a loadable Operating System image (`MPM.SYS`) for your computer.

I have replaced the use of `GENSYS.COM` to produce the final image. The
assembler build process now directly produces the required `MPM.SYS` file. I
still use the `MPM.COM` loader program to execute this, so the final `MPM.SYS`
layout must still adhere to the original specifications.

My next step is to better understand the code and see what can be done to solve
the bank switching challenge.
