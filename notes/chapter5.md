---
layout: default
title: Chapter 5 - Firmware
nav_order: 4
permalink: /chapter-5
---

Chapter 5 - Firmware
====================

* A computer is just a CPU, RAM, a bus.
* You need some way of interacting with a computer.
    * Keyboards, mice, monitors, sound, all that.
* How does the computer "talk" to all the other devices?
* Extend the data bus throughout the rest of the computer.
* Early mobos were covered in chips, but eventually, they coalesced into a paired set of chips. *northbridge* and *southbridge*.
* The pair is called the *chipset*.
* Until around 2010, they were paired chips.
* But now, memory and display controllers are built into CPUs, so there's really only one chip. *Platform Controller Hub*
* Basically, the chipset extends the EDB to the every other device on the system.
* The CPU talks to this bus to move data to and from everything.
* The address bus extends to the rest of the system via the chipset.
* Okay, so how do we know what to put on the address bus?
    * Consider the interaction between keyboard and CPU.
    * Keyboard controller accepts commands just like the CPU. It's basically a microprocessor.
    * So the CPU needs to know what command to put on the bus to get tell the keyboard controller to get the scancode of the last key pressed.


## BIOS

* The CPU doesn't know how to talk to anything at first.
* It needs some basic programming loaded into memory that teaches it how to talk to a device.
* Every time you press a key, the keyboard notices it and sends a *scancode* to the keyboard controller.
* {: .label .label-yellow}Note, occasionally, you'll hear people talk about different controllers. But these are all integrated in the chipset.
* How does the CPU get the scancode out of the keyboard controller?
* The CPU needs to know what command to send to controller to get the most recent scancode.
* We call this *basic input/output service*. BIOS
* These programs are called *services* or *device drivers*.
* Every device on the system needs some sort of BIOS. Some little program that teaches the computer how to use it.

## ROM

* Where do we store the program for a keyboard?
    * The OS?
    * Yes and no.
    * What about before the OS is loaded?
    * CPU needs to talk to these devices before the OS is loaded (or even installed).
    * Let's put this support programming directly on the mobo.
    * But how to store it? DRAM?
* Mobo stores programming on a device called a *read-only memory (ROM) chip*.
* ROM are *nonvolatile*
* ROM is read-only.
* Modern mobo use a ROM called *flash* ROM.
* It can update and change by "flashing the ROM". (more later)
* *system ROM* chip enables CPU to talk to all basic hardware of the PC.
* hard drives, optical drives, USB ports, displays, mosue, etc.
* Hundreds of little services (2 to 30 lines of code)
* All of these together are called the *system BIOS*
* any program stored on ROM is called *Firmware*.
* difference between firmware and software?

## System BIOS support

* It must support both the hardware the never changes, but also the things that might change from time to time.
* But it also needs a place to store state information about the hardware that is currently installed.

### UEFI

* Unified Extensible Firmware Interface

## CMOS and RTC

* Where can it store settings that don't have to be re-entered every time, but can change?
* It's a little bit of RAM hooked to a battery.
* *complementary metal-oxide semiconductor (CMOS)*
* It stores BIOS settings, as well as handle the *real-time clock*.
*
