# Green Series FAQ

### What kind of backplanes can i use - do I have to use this green one?

You can use any RCBus compatible backplane that supports all 80 bus lines.  You can even use non-green ones!  Just make sure it has the full 80 lanes (2x40 pin headers)


### How do the Linear and the normal Memory Modules work together

The independent selection of the 2 types of memory modules by the eZ80, is managed by use of its Chip Select (CSx) control signals. The eZ80 has four of these signals (CS0 to CS3). Only one of these signals will be activated at any given time – they are configured for specific addresses within the eZ80’s 24 bit addressable range.

The CSx signals are wired such that CS3 is connected to the standard 16 bit paged 512K ROM/RAM module (or any Z80 RC2014/RCBus memory module), and CS0 is connected to the linear memory module.

The 2MB linear module only activates when the eZ80’s CS0 (chip select 0) is triggered.

Whereas the standard 512K ROM/RAM modules is triggered by the MREQ line of the RCBus. The MREQ line is driven from the eZ80’s CS3 signal.

The firmware flashed into the eZ80 will on boot, configure the CS0 and CS3 to only activate at specific non-overlapping addresses.

When the eZ80 addresses the 24 bit range from 0x030000 to 0x03FFFF - it will activate the CS3/MREQ control line - therefore the standard 16 bit memory modules will be selected.

When the eZ80 addresses within the 24 bit range of 0x200000 to 0x3FFFFF, the CS0 signal is activated, thus the linear memory module is selected (and the normal memory module will not activate).

When the eZ80 is operating in Z80 compatibility mode, although the code executing only sees a 16 bit address - its been configured to map to the CS3 range of 0x03XXXX.

The CS0 and CS1 are wired onto the RCBus pins 48 and 47, respectively.

The firmware of the eZ80, in addition to managing the CSx configuration, will assume there is a standard ROM available. It will configure itself to run in Z80 compatibility mode then jump to the ROM (typically RomWBW). That code will then execute, unaware for the most part, that it is running on an eZ80.

### Whats the memory layout of the eZ80

The eZ80 has a 24 bit address bus, so it can address upto 16MB of Memory without the need for bank switching.

The firmware you flash, supplied from the github repo [https://github.com/dinoboards/ez80-for-rc](https://github.com/dinoboards/ez80-for-rc) configures the eZ80's memory timings and addresses to the following layout:


| Address Range    | Description |
| ---------------- | ----------- |
| 000000 -> 01FFFF | ON-CHIP ROM |
| 02E000 -> 02FFFF | ON-CHIP RAM |
| 030000 -> 03FFFF | EXTERNAL ROM/RAM (CS3) FOR Z80 COMPATIBILITY MODE |
| 200000 -> 3FFFFF | EXTERNAL LINEAR RAM (CS0) 2MB |
