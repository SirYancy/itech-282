---
layout: default
title: Chapter 6 - Motherboards
nav_order: 5
permalink: /chapter-6
---

Chapter 6 - Motherboards
========================

* The motherboard
    * Foundation of the computer
    * Everything plugs into it.
    * It contains wires *traces* which are the buses
    * It holds all the ports used by peripherals
    * Distributes power from the power supply
* Motherboards are layered PCBs
* Three characteristics
    * form factor
    * chipset
    * components
* Form factor is the physical size of the mb. Also indicates where some components are located.
* Chipset defines type of processor, RAM and determines the built-in devices the mb supports
* Built-in components define basic functionality
* Almost all chipsets are are Intel or AMD
* Exam focuses primarily on mb that are designed for Windows/Linux computers.

# Form Factors

* Form factor determines location of components and overall size and shape of the board
* Applies to MB, case, and power supply
* Start with AT

## AT

* Big
* Lacked external ports
* Only dedicated port was for keyboard
* But it couldn't kee up.

## ATX

* 1995
* This is the most popula one.
* keyboard ports replaced with rear panel.
* Replaced AT keyboard port with PS/2 or USB
* CPU and RAM are easier to access
* RAM is closer to CPU and chipset/northbridge
* Full ATX is 12 x 9.6 inches
* MicroATX is 9.6 x 9.6
* The exam refers to MircoATX as mATX.

## ITX

* ITX form factor was not a success, but its cousin Mini-ITX, 6.7x6.7 inches competes with MicroATX

## Proprietary Form Factors

* Exist

# Chipset

* Typically today, most of the functionality of NB/SB has been consolidated in one chip.
* But to support some legacy hardware, some manufacturers add Super I/O chip
* Largely terms SB and NB are dead
* So. System ROM provides basic generic support for chipset, etc
* But where do we get BIOS for expansion devices?
    * Software drivers loaded into the OS
* Most Mobos ship with a CD with software device drivers, etc
* Different chipsets support different devices.
    * See diagram in text of Z390 chipset

# Standard Components

* Every mobo has a socket (2?) for CPU. Slots for RAM. 
* There are also going to be ports to support mass storage (more in chap 8)

## Additional Components

* Chipset determines what can be on the mobo.
* Sometimes, manufacturers might not include all chipset features on the mobo itself
* Or, there might be added features not supported by chipset, but with thier own dedicated chips (maybe an old serial port)
    * Things like old serial ports
    * RAID controllers
    * Sound
    * network cards, etc
* Other convenience features like fan power connectors and lights and other fun stuff.

## USB

* All chipsets support USB.
* But they're all going to be different in port arrangement
* So there might be sockets (headers) to plug in additional ports.
* Some external USB ports are standardized (case connectors)

## Sound

* Onboard sound support is also common.
* Front panel audio jacks supported
* back audio jacks as well

## Networking

* RJ-45 jacks.
* Networking will be built into chipset or an additional chip.
* Chapter 18

## Video

* One or more video ports
* THey Vary
* CHapter 17

## RAID

* *redundant array of independent (or inexpensive) disks*
* Chapter 8

## Case Fan Support

* Every mobo has a CPU fan power connector. 
* But there may be connectors for case fans.
* Sometimes these case fans can be controlled from Windows

# Expansion Bus

* Every device connects to external data bus and address bus
* Expansion Slots as well
* *Generally*
    * Older expansion bus connects to chipset
    * Newer expansion bus connects to CPU
* But many systems have both.
* Anything you plug into an expansion slot acts as if it's soldered to the system
    * Except slower
* Remember, system crystal synchronizes entire system (chipset, etc)
* Every other chip also has a CLK wire.
* However, if this worked for the expansion bus, you'd have a problem.
    * expansion cards would need to be specifically made for specific system speeds
* So, this extended bus, runs at its own *standardized* speed. Expansion buses have their own crystals
* These slots run much slower than frontside bus
* Chipset is a divider between these two buses
* Originally, very slow, 7.15 MHz.
* Let's look at what it's like today

## PCI

* *Peripheral Component Interconnect*
* Intel made PCI public domain
* Original PCI was 32 bits wide, 33 MHz.
    * It played nice with older expansion buses
    * Self-configuring (plug and play)
    * burst mode

## Mini-PCI

* Laptop version
* older computers

## PCI Express

* *PCIe*
* Still PCI, but uses a point-to-point *serial* connection, instead of shared *parallel* communication.
* Think about why a serial connection might be faster than a parallel connection
* Sending and receiving wires for serial data. Each pair is called a lane.
    * Each direction runs 2.5 gigatransfers per second (GTps) on PCIe 1.x
    * PCIe 2 gets 5 GTps
    * PCIe 3.x gets 8 GTps
    * PCIe 4.x gets 16 GTps
* Each p2p connection can use 1,2,4,8,12, or 16 lanes. Up to 256 GTps.
* *transfer rate* describes number ops happening per second
