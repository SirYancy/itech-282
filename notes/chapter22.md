---
layout: default
title: Chapter 22 - Virtualization
nav_order: 14
permalink: /chapter-22
mathjax: true
---

Chapter 22 - Virtualization
===========================

# Virtualization vs Emulation

* Virtualization takes the hardware of the host system and allocates some portion to a virtual machine.
* No matter what you do, though, it will always act like the host system. 
    * An Intel system can never actually act like a Nintendo
    * The hypervisor is just going to pass code from the virtual machine to the CPU
* Emulation is different.
* An emulator converts commands to and from the host machine into an entirely different platform.
* You can run super nintendo games on a windows machine, for example.
* One thing to keep in mind: emulating another platform requires a lot more power than the original platform being emulated.

## Client-Side Virtualization

* *Client-side virtualization* is running the virtual machine on your local system. The VM file itself might be stored locally or on a server accessed via network
* Process looks like this:
    1. Set up system's hardware and verify it can meet the resource requirements
    1. Install a hypervisor on your system
    1. Create a new VM that has the right hardware requirements for guest OS
    1. Start the new VM and install the guest OS as if you are putting it on a physical machine.

### Hardware Requirements

Any computer can run a VM. But hardware virt support is a big bonus. Intel CPU: *VT-x*. AMD CPU: *AMD-V*.

You also need RAM. Lots of it. If you're planning on doing any virtualization, you should have as much as possible.

* Leave enough RAM for the hypervisor to run
* Add enough for every VM you want to run

### Storage

You need a place on the HD for the VM to live as well. Something like 10+ GB? Why would you need less for a VM than a host OS?

Consider:

* Having room to grow
* Protect them with RAID and backups
* Consider SSDs

# Networking

* Internal networking and its applications (testbed type things)
* Bridged networking. The virtual NIC bridges to the real network of the host machine
* 

