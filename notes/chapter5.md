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
* Let's rename the MCC. Let's call it the *Northbridge*.
* It's the primary bridge between the CPU and the rest of the computer.
* *Northbridge* is the connection to high speed devices like RAM and video card.
* The *Southbridge* deals with slower connections like USB, hard drive, and other slower controllers.

* {: .label .label-yellow}Note: A lot of NB functions are now directly on the CPU and the SB is called different names:
    * *Input/Output Controller Hub* by Intel
    * *Fusion Controller Hub* by AMD.
    * Some systems move SB to *Platform Controller Hub*.
    * That said we still use the names Northbridge and Southbridge to refer to some of these functions.
* Together, we call the NB and SB the *chipset*.
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
* We call this *basic input/output service*. BIOS
* These programs are called *services* or *device drivers*.
* Every device on the system needs some sort of BIOS. Some little program that teaches the computer how to use it.
* Where do we store the program for a keyboard?
    * The OS?
    * Yes and no.
    * What about before the OS is loaded?
    * CPU needs to talk to these devices before the OS is loaded (or even installed).
    * Let's put this support programming directly on the mobo.
    * But how to store it? DRAM?

## ROM

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

* 
