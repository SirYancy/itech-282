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
* **Entering IP Info**
    * Every computer that wants to connect to a network must know:
        * **IP address**
        * **Subnet Mask**
        * **Default Gateway**
        * **DNS server**
    * You can enter this information statically or dynamically.
    * YOu can do it manually.
    * But it's easier to obtain an IP address automatically.
    * This works if your network uses *DHCP - Dynamic Host Control Protocol*
    * Most networks do.
    * When your computer boots, it broadcasts a DHCP request. the DHCP server gives you all the IP info it needs.
    * You can also manually configure, creating a *static IP address*

## TCP/UDP

* A TCP/IP connection is either connection-oriented or connectionless.
* Advantages and disadvantages of them.
* Connection-oriented: TCP
* Connectionless: UDP
* *You* don't choose one or the other. The needs of an app dictates which protocol gets used.
* TCP: Ensure that every bit of data gets there.
* UDP: Fire and forget

## TCP/IP Services

* TCP/IP is good at routing traffic efficiently. Two computers on different LANs can talk.
* Traffic is not sent to the router unless the connection is between two different LANs.
* All of these decisions are made based on destination IP address of packet.

## TCP/IP Settings

* You don't need to know how to derive correct settings, but you do need to know where to enter them. (1002)

## TCP/IP Tools

* 
