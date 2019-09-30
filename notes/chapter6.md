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
* Depending on how it's encoded, you can lose some effective data rate because it has to be decoded and reassembled at the other end.
* Still, duplex communication on x16 can be 32 GBps
* Most common is the PCIe x16 slot. Typically for graphics cards. And not really much else need that much throughput.
* Also common are x1 and x4 PCIe slots

## Installing Expansion Cards

Four main steps

1. *Knowledge* - Know what you are installing. Compatibility. OS. Drivers. For new versions of Windows, the answer is usually yes. But for older hardware or uncommon OS, this is not a guarantee.
1. *Physical Installation* - Two places: In a computer or an anti-static bag. Hold only by the edges. Don't touch the pins. Don't touch any of the components. Use anti-static wristband or at least ground yourself after removing it from the bag. Since the mobo always has a trickle of power, *always unplug the computer*. Lock it in with a screw or other mechanism. Some cards actually use this screw connection to ground it. If you *have* to clean the pins, use a can of air. There's also electronic cleaning solution. If the motherboard is seated correctly, the card should sit in the case very nicely.
1. *Device Drivers* - Installed automatically by the OS. Occasionally, an optical disc. It's usually fairly straightforward, or automatic. But it is possible to make mistakes.
1. *Verify* - Check if it works as intended.

* Usually, you'll find more recent drivers on the manufacturer's website.
* Usually, you have to install the device first, and then install drivers or you'll have errors
    * Except for some USB devices where you want the driver first. (not always)
* Sometimes you have to remove old drivers before you install the new device. Locate in the Device Manager.
* It is possible to get unsigned drivers
* Driver rollback is also a thing.

# Troubleshooting Expansion Cards

* Botched installations are the main cause of problems here.
* If the device doesn't work: Reinstall (after checking the device manager)
* If it doesn't show up in the device manager, check that it's installed properly and has power.
* `hdwwiz.exe`
* At this point if it still doesn't work, the device might be damaged.
* Or it's turned off in CMOS.
* Black ! in device manager.
    * Check it's installed correctly
    * Try the **Update Driver** button.
* Black downard pointing arrow.
    * Device is manually disabled or damaged.
    * Check if it's disabled.
    * Try rolling back the driver
    * Or Uninstall
* If none of this works, the card is probably bad.

# Upgrading and Installing MOtherboards

* First decide AMD or Intel
* Then Form Factor
* Then features and easy of configuration
* Then actually select the case
* Step By Step
    1. What motherboard do you need?
        * CPU?
        * How much RAM are you going to have?
        * Not a bad idea to get to know some of the names of popular manufacturers.
    1. Get the form factor that works with your case
    1. Read the motherboard book.
    1. Pick your case carefully. 
        * Lots of different sizes.
        * slimline, desktop, minitower, mid-tower, cube.
        * Also specialized cases
        * Sometimes they come with PSUs.
        * Verify wattage
* Installing the motherboard
    * Remove all of the cards.
    * Remove anything else that might impede removal or installing of mobo. HDDs etc
    * Keep track of screws
    * Unscrew the motherboard.
    * Remove the old motherboard.
    * Verify that all the correct standoffs for the new mobo are there.
    * Next: connect the LEDs, buttons, front mounted ports. (sometimes easier before you install in the case)
        * soft power button
        * reset button
        * speaker
        * hard drive activity light
        * power light
        * usb
        * sound
        * thunderbolt
    * Make sure you watch +- connections with these as lights are LEDs.
        * Don't worry, you can't break anything though.
        * Only the power button is absolutely necessary
    * Now, Install new mobo
    * Install CPU and RAM
    * Connect power to everything
    * See if it POSTs.
* If it doesn't POST.
    * If you get no power, check to make sure you plugged in all power connectors
    * If you get fans but nothing on the screen
        * CPU, RAM, or Video Card
        * Just test

# Troubleshooting Mobos

* 
