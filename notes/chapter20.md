---
layout: default
title: Chapter 20 - Wireless Networking
nav_order: 12
permalink: /chapter-20
mathjax: true
---

Chapter 20 - Wireless Networking
================================

## Historical/Conceptual

* Lots of different wireless communication solutions.
    * radio waves
    * infrared
* Today, most wireless radio networks:
    * IEEE 802.11 wireless Ethernet standard
        * Marketed as Wi-Fi
    * Bluetooth
    * Infrared Data Association protocol
    * Cellular networks
* For many years IR was popular on almost all devices, but has fallen out of favor
* Now, we see Wi-Fi and bluetooth most commonly.
* Almost always integrated. Sometimes add-on
* Sometimes it's an add-on card or USB wireless NIC
* Almost all devices have some kind of wireless capability.

## Info

* You need a wireless access point (WAP) (also just *AP* or *access point*)
* Many WAPs act as switches and routers as well.
* most draw their power from wall outlets, but *PoE* is common in many corporate networks.
    * PoE is also useful for things like security cameras.
* Bluetooth is built-in in most cases, but can be an add-on (usually via usb dongle)
* Common application: connecting wireless speaker to a phone. Also wireless keyboards and mouse

### Wireless networking software

* Wireless uses the same networking protocols and client software that wired counterparts use.
* They use a *carrier sense multiple access/collision avoidance (CSMA/CA)* networking scheme (this acronym not on exam objectives)
* Basically a wireless node checks to see if anything else is broadcasting. If it hears something, it waits a random time period before trying again.
* It has the option of sending RTS/CTS frames, but this introduces a lot of overhead.
* Configuring is typically easy. Everything is typically plug and play
* You will probably have to set network name and other parameters when setting up a connection.
* Windows and MacOS have utilties built-in to do this, but some vendors have their specific software for configuring their devices.

### Wireless network Modes

* **Ad Hoc Mode**
    * peer-to-peer
    * each node in direct contact with each other node.
    * Two or more nodes in ad hoc form an *Independent Basic Service Set (IBSS)*.
    * Work great for small groups that need to share files, printers, maybe for study groups or business meetings.
    * Windows has this option disabled by default on all modern versions (8.1+)
* **Infrastructure Mode**
    * one or more WAPs to connect nodes to a wired segment.
    * This is called a *Basic Service Set (BSS)*
    * You can extend it by adding more WAPs to create an *EBSS*.
    * Better suited to networks that need to share dedicated resources such as
        * internet connections
        * centralized databases
    * Great for SOHO.
* A mention of *Wireless Mesh Networks* is appropriate

### Speed and Range Issues

* Depends on several factors
* Most important is standard that each device uses.
    * range from 2 Mbps to 1+Gbps
* Distance between nodes
* top speed is dynamically negotiated between devices.
* Less than 25 ft is typically maximum speed
* At outer edges, it might only be 1 Mbps
* Interference caused by solid objects and other wireless devs in same freq range
    * cordless phones, baby monitors
* Dead spots can occur when things block signal.
    * Large appliances like refridgerator
    * also fuse boxes, metal plumbing, AC units, etc
* You can never really know speeds and ranges until the device is set up and tested.
* Effective range is usually about half what is listed
* increase range by 
    * installing multiple WAPs to permit "roaming"
    * Install a replacement WAP with higher range
    * signal boosters or *wireless repeaters/extenders*.
* There will be questions dealing with issues about wireless connectivity. Basic common sense is usually all you need for these.

## Wireless Networking Standards

* 
