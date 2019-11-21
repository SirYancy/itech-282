---
layout: default
title: Chapter 19 - Local Area Networking
nav_order: 11
permalink: /chapter-19
mathjax: true
---

Chapter Chapter 19 - Local Area Networking
==========================================

# TCP/IP

* *Ethernet*'s job is to move data from one machine to another.
* An Ethernet frame is max 1500 bytes. What if you need more?
* What if you replace a network card (and the MAC)
* *Network Protocol* software keep sall this data organized.
* Lots of these have been invented over the years.
* Often simple protocols are combined into a *stack*.
* *Transmission Control Protocol/Internet Protocol* is the most important one.

## Network Adressing with IPv4

* *IP address* identifies the node and network on which it resides.
* **IP Addresses:**
    * Unique identification number for your system.
    * Most use *IPv4*
    * What's your IP address?
    * Consists of four sets of 8 binary digits (octets) separated by periods.
    * To make it easier: *dotted decimal notation*
* **Submet Mask:**
    * Two parts: *Network ID* and *Host ID*.
    * The NIC uses a *subnet mask* to tell which part is which.
    * Example:
        * IP address: 192.168.4.33
        * Subnet mask: 255.255.255.0
    * *Every computer on a single LAN must have the same network ID and unique host ID.*
    * *IP conflict* is when two hosts have same address.
    * IP addresses never have 0 or 255 in them.
    * How many computers can connect to a network with subnet mask 255.255.255.0?
    * IPv4 uses the *Classless Inter-Domain Routing (CIDR)* system.
    * Go over example in text. p 836
* **Interconnecting Networks:**
    * IP addressing allows interconnecting of network IDs.
    * This makes larger *WANs*
    * Interconnecting requires a *router*.
    * The router filters and forwards by IP address.
    * One a router, one port connects to your switch.
    * The other port connects to some other network (like ISP)
    * The router's LAN-side IP address is called *default gateway*.
* **DNS**
    * Talk about DNS and domains.
* 
