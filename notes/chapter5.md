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

## Typical System Setup Utility

* All manufacturers have their own system setup utilities.
* But, they are all largely the same. The most important thing to remember is to read options carefully and *not save* unless you are sure you set something correctly.
* Mouse-based navigation in UEFI/BIOS setup utilities became commonplace several years ago now.
* Laptop demo. Press delete to get into BIOS
* Look through all the settings and discuss

### BIOS Security Settings

**Chassis intrusion detection/notification**
: Cases can contain a switch that trips when someone opens the case.

**LoJack**
: Security feature in firmware. If your PC is stolen, you can track its location, install a keylogger, or shut down computer.

**Trust Platform Module**
: TPM acts as secure cryptoprocessor. hardware for accelerated cryptographic functions and secure storage. Many companies use it in their hardware. Things like *BitLocker* in MS Windows can be accelerated by TPM.

* {: .label .label-yellow}security questions can include: TPM, passwords, secure boot, intrustion detection, drive encryption

### Exiting and saving settings

* You can save and exit, or exit without saving.

### Option ROM and Device Drivers

* BYOB (Bring your own BIOS)
* Option ROM
    * Things like RAID controllers, etc
    * Put BIOS on device itself. 
    * CPU doesn't know how to talk to a device 
    * Most devices do not come with option ROMs these days.
    * Except Video Cards
* Device Drivers
    * This is a small program which contains the instructions for the device
    * Run by the OS
    * Two ways to get Drivers
        * It may come on some install media (CD, etc)
        * More likely, downloaded from the web when the device is detected by the OS
    * They are stored in the *Registry*

### Everything needs BIOS

* Lots of places BIOS might be.

## POST

* On power up
* A program on the ROM chip
* Checks out the system every time it boots.
* It sends a command to all systems
* standard devices run their own built-in diagnostic
* Devices are resonsible for their own diagnostic. Your system does not police this.
* What can POST do when something goes wrong?
    * Tell an adult
    * Beep codes and text messages

## Beep codes

* The motherboard can't tell you anything during boot up (no BIOS loaded).
* So it would beep at you.
* You could find beep codes in motherboard manual
* Modern PCs have two beep codes (typically)
    * bad/missing video: long beep, followed by 2 or 3 short beeps
    * bad/missing RAM: short beep that repeats indefinitely
* Other possible beeps
    * most PCs will do a single beep when all is well
    * Sometimes you'll hear strange sounds if the CPU overheats, or RAM is seriously damaged/missing. (not related to POST)

## Text Errors

* These are messages that display on the screen.
* Self explanatory

## POST Cards

* There are peripherals that can help you diagnose device problems if the POST fails.
* usually has a 2 character LED that can tell you which device is acting up.
* Usually not an essential tool in the box these days. Just a way of testing just how dead a computer is.

### Boot Process

* "Pull yourself up by your bootstraps"
* The process
    * Power Supply has power! it checks itself out
    * It sends a *power good* signal down a special wire to wake the CPU
    * CPU's first act is to send a special address to the address bus. The address of the first command of the BIOS program.
    * This starts the POST
    * After this, it can go one of two ways
        * Old BIOS: POSt passes control to last BIOS function: bootstrap loader. This program finds the OS. Reads info off CMOS. So it'll basically read your *boot sequence* to see which disk to look for an OS. Almost all HDDs and other media have a boot sector (special location set aside for this). If there's a program there which points to an operating system, it's said to be a bootable drive. If the bootstrapper finds an OS, it hands over control and deletes itself from memory. If it doesn't it'll go down the list or return an error.
        * UEFI: POST hands control of boot process to a *Boot Manager*. The UEFI firmware stores all the boot configuration directly, rather than having to use bootloaders, etc.
        * Other option: *preboot execution environment*. Getting OS from a server

## Care and feeding of BIOS/UEFI and CMOS

* Messing around with CMOS settings is where a lot of problems can start.
* Only make as many changes as you can remember. Document everything.
* Don't make  any changes unless you know what they do

### Default/Optimized Settings

* Reset options in CMOS.
* They keep you from having to memorize a lot of weird stuff
* Default settings are  fail safe, very simple set.
* Optimized settings are theoretically, best possible speed/stability for the system

### Clearing CMOST RTC RAM

* If you mess things up, even badly (so the system is essentially dead)
* Almost every mobo has a set of wires called CLRTC
* Procedure:
    * Turn off and unplug the computer
    * Find the clear wires
    * Move the shunt (jumper) from wires 1 and 2 to wires 2 and 3.
    * Wait for 10 seconds
    * Move the shunt back
    * Plug in and boot the system.
* If that doesn't work (or if no CLRTC), you may have to just pop the battery out.

## Losing CMOS RTC Settings

* Typically, systems use a CR2032 battery (3v lithium coin battery)
* If something goes wrong, the system might give errors or not boot
* Generally, low probability of not booting but...
* Possible errors that might come up:
    * CMOS configuration mismatch
    * CMOS date/time not set
    * BIOS time and settings reset
    * No boot device available
    * CMOS battery state low
* Reasons for losing settings?
    * Pulling and inserting cards
    * Touching the motherboard
    * Dropping something on the motherboard
    * Dirt on the motherboard
    * faulty power supply
    * electrical surges
* If the system clock keeps going back to January 1, it's a good sign that the battery needs to be replaced
* To preserve settings, you can leave the system plugged in, but *be very careful about ESD if you do this*.

## Flashing the ROM

* Firmware updates (exam terminology)
* "flashing the BIOS"
* This can add support for new technology
* Typically, you download the update file from the manufacturer website
* Stick it in a USB drive
* Boot into CMOS settings
* Run the BIOS update utility.
*
