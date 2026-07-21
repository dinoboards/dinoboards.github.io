---
layout: post
title: MP/M 2.1 running on the eZ80 - lots of chewing
tags: eZ80 Green RC2014 RCBUS CPM

---

*"Bite off more than you can chew, then chew like hell"* - Peter Brock

## I am chewing...

In my last post, I discussed converting the source code from Intel to Zilog instruction format and consolidating the MP/M code into a single build process using the GNU Assembler for eZ80.  I verified the created binary file is still the same, and so I can now contemplate modifying the code to take advantage of the eZ80's extended instructions.

## The 64K Bank Switching Problem

Also mentioned previously, running my MP/M port on the eZ80 has a massive performance issue with the context switching logic.

A typical Z80 MP/M setup would leave memory above 0C000h (the top 16KB) unbanked. This upper area holds core (or common) parts of the operating system that must remain the same, regardless of which program is running in the lower 48KB.

As my eZ80 does not have a banked memory system, I rely on its Z80 compatibility mode and use 64K memory segments.  I can select any 64K segment from the available memory, but it's always a full separate 64K of memory that's selected.

To make MP/M work, I had to simulate a memory banking system.  When MP/M needs to do a bank change, I made the code change to a new 64K segment and copy over the top 16K or so of memory from the old segment.  Thus simulating changing just the lower 48K of memory.

I use the very fast ***LDIR*** block copy instruction.  This single instruction can copy a lot of memory quickly, far quicker than a Z80 - but its just not fast enough for the job.  Doing the copying every time the system switches from one process to another (perhaps 60 times a second), causes a significant slowdown.

Of course, the eZ80 doesn't actually need traditional bank switching. It can natively access any memory location it wants, even while running in Z80 compatibility mode.

Consider the following Z80 code to load the A register with a value stored in memory:

<pre style="margin-left:1em; margin-right:1em;  padding:0px;line-height:1em">
<code style="font-size:0.8em">
  LD A, (3400h)       ; Assembles to: 3A 00 34
  RET                 ;               C9
</code>
</pre>

This standard Z80 code reads the byte at memory location 03400h into the `A` register. The address is a 16-bit number, so we can only access memory in the current active 64K segment.

But using the extended instructions of the eZ80, we can also have:

<pre style="margin-left:1em; margin-right:1em;  padding:0px;line-height:1em">
<code style="font-size:0.8em">
  LD.LIL A, (3A4500h) ; Assembles to: 5B 3A 00 45 3A
  RET                 ;               C9
</code>
</pre>

The `.LIL` instruction suffix causes the assembler to prefix the load instruction with the special byte 05Bh. This prefix code forces the processor into its extended mode for the next instruction only. The CPU then expects a 3-byte address, allowing us to read from anywhere in the eZ80's linear address space.

## Updating the code

There are a few things I have started to convert in the code, to take advantage of the eZ80's capabilities.

### Small things

Throughout the code, there is a lot of code that can be optimised with the extra instructions the Z80 and the eZ80 have over the original Intel 8080.  Things such as the following:

<pre style="margin-left:1em; margin-right:1em;  padding:0px;line-height:1em">
<code style="font-size:0.8em">
  LD      E, (HL)
  INC     HL
  LD      D, (HL)
</code>
</pre>

This can be replaced with:

<pre style="margin-left:1em; margin-right:1em;  padding:0px;line-height:1em">
<code style="font-size:0.8em">
  LD      DE, (HL)
  INC     HL       ; dropping this increment if it's not needed
</code>
</pre>

I can also consider using the IX and IY registers, although I probably need to ensure they are saved/restored on the stack, as potentially existing applications may assume IX and IY don't change under MP/M.

There are a few other patterns like this, small simple things that won't really make that much difference.


### The SPL Stack and 24-bit registers.

When MP/M performs a context switch from one application to another, it does this by saving and restoring all the registers and the Stack pointer.  That means when a process resumes from where it left off, as far as the program is concerned, nothing has changed.  This context persistence is not just needed for applications - lots of code within MP/M will potentially undergo a context switch, and bad things will happen if registers or the stack are not consistent.

This is a problem if we start to use eZ80 extended 3 byte registers and the eZ80 extended long stack (SPL).  I need to update the context switching code to also persist and restore the  eZ80 upper byte of the registers, and also most importantly, the 2nd stack that the eZ80 has for its extended addressing mode - the SPL.

I thought this might be relatively easy.  Within MP/M there is a ***Process Descriptor*** structure.  A 52 byte long structure that holds various bits of data about a process, its location in memory and its registers and the current stack pointer.  As processes are switched over, the register and the stack are stored in its ***Process Descriptor***.

The structure is a linked list - so each ***Process Descriptor***, points to the next one - and the last one has a NULL pointer (zeros).

So I updated the code to add 3 extra bytes to this structure for storing the SPL.  (I will worry about the registers later).  It all worked perfectly.  The SPL pointer was being stored and restored as the processes switched - except, that is, when I ran the  `MPMSTAT` utility program.  This program, a tool from Digital Research, lists a bunch of operating system stats - memory, queues, paused processes and a list of currently running processes.

I noticed that the name it would report for each of the running programs were garbled.  The first listed its name fine.  The 2nd program's name had 3 garbled characters, the next one had 6 garbled characters and so on.  There was something that was not respecting the new size of the **Process Descriptor**.

Although these ***Process Descriptors*** are stored in sequence - they are meant to be discovered through the linked list pointers.  But it seems the MPMSTAT program was just assuming these structures are always 52 bytes long.

Unfortunately, the source code for MPMSTAT does not seem to exist anymore - I disassemble the program, and also debugged it step by step - and yep - there are places where its just assuming that the structures are in sequence and are exactly 52 bytes long!

So I have a choice - break MPMSTAT (I could probably write a new one) - I do wonder if other programs might also make this assumption - I want to ensure my system is as compatible as possible.  I will have to have a think about this.

> [Chris Brock's port of MP/M to eZ80](https://github.com/cbrock487) has also changed the *Process Descriptor* structure.  I am not able to run his code - so dont know if his port also has the same issue with MPMSTAT.

The code for all these changes is not yet included in the main line or main release on my repo.  But its on a branch and available from the CI builds at <a href="https://codeberg.org/dinoboards/ez80-for-rc/actions" target="_newwindow">https://codeberg.org/dinoboards/ez80-for-rc/actions</a>

## Yeah nah, yeah

So many things to work through

* How am I going to avoid the need to copy memory when context switching?
* How will I persist the eZ80 registers and SPL and still be fully compatible?
* I sure dont want to rewrite the entire code base - arg!

I am not sure what the answer is to these and other questions - But for the time being, I am just gonna keep chewing like hell - and hope I get there.


