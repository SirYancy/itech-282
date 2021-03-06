---
layout: default
title: Chapter 19 - Local Area Networking
nav_order: 11
permalink: /chapter-19
mathjax: true
---

Chapter 19 - Local Area Networking
==================================

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

* Connection-oriented vs Connectionless
* *User Datagram Protocol*
* Fire and forget protocol.
* Useful for VOIP, streaming video, and things where dropped packets aren't a problem.
* UDP is very fast.

### TCP/IP Services

* TCP/IP services are other functions under the umbrella of TCP/IP
* Example HTTP and the WWW
* Other services include SSH
* TCP/IP links any two hosts whether they are on the same LAN or not.

### TCP/IP Settings are saved for next course

## IPv6

* We have a problem.
* IPv4 is 32-bit. This means we can address 4 billion addresses. Plenty in 1970s.
* IETF developed *Internet Protocol version 6*.
* Address is 128 bits. That's %2^128$ addresses. Estimated to half the grains of sand on Earth. 1/8 of all molecules in Earth's atmosphere.
* Demo on [repl.it](https://repl.it)
* Significant differences. Let's go over it.
    * Notation
        * 128-bit IPv6 addresses look like this:
            ```
            2001:0000:0000:3210:0800:200c:00cf:1234
            or
            fe80:0000:0000:0000:7f26:024d:9a58:c412/64
            ```
        * Colon instead of dot as delimiter
        * Each is a hexadecimal number between 0000 and ffff
        * Each is called a *field* or *hextet*. (Unofficial)
        * 8 groups of 4 hex chars.
        * There are ways to shorten these.
        * Rules for shortening (they are kinda long)
            * Leading zeroes can be dropped.
                ```
                2001:0:0:3210:800:200c:cf:1234
                or
                fe80:0:0:0:7f26:24d:9a58:c412/64
                ```
            * Remove any number of consecutive groups of zeroes and leave a double colon. But only once.
                ```
                2001::3210:800:200c:cf:1234
                or
                fe80::7f26:24d:9a58:c412/64
                ```
            * Special "loopback" address is `::1`
            * IPv6 uses `/x` for prefix length. This is basically the same as CIDR IPv4 Mask
            * [Check the sim](http://totalsem.com/100x)
* Where do IPv6 address come from?
    * Link-local addresses in IPv4 usually mean that you have lost a network connection.
    * But in IPv6, every computer has a link-local address.
    * This is the first 64 bits: fe80:0000:0000:0000
    * The next 64 bits is the *interface ID*. Currently, it is random. Old OSes used the MAC address to generate it.
    * Link-local is basically for all local networking needs.
* IPv6 prefix lengths
    * *prefix lengths* are used to determine whether to send packets to a local MAC or ot the default gateway.
    * Last 64 bits are generated by the NIC. Leaves a maximum of 64 bits for prefix. ie: no prefix is longer than /64
    * Five Region Internet Registries (RIRs) pass out /48 prefixes to big ISPs and end users with large allotments
    * They will then borrow another 16 bits for subnetting pass out /64 interface IDs to end users. Link-local is always /64.
* Global Unicast Address
    * To get to the internet, you need a global address.
    * When you boot up. You send out a RS message.
    * A router hears it and sends a RA message.
    * This message has your network ID and subnet (together this is the prefix) and a DNS server (if available/configured)
    * This RS messages go to ff02::2. This is only for other machines on the network. It's called a *multicast address*.
    * Once you have the prefix, you generate your own address. You will get your own link-local and public IPv6 address.

# Troubleshooting

* A+ only asks about getting single computers back onto the network.
* The exam will ask scenario questions with "no connectivity" or "intermittent connectivity".
* The first is *usually* something physical (on the exam). The second is when you can't access some specific resource that you want.

## Repairing physical cabling

* Physical networks rarely go down. But what do you do when they do?
* Symptoms
    * Windows has a red X over the network icon.
    * First check the obvious (run ipconfig)
    * Do you see the APIPA/zeroconf address (169.254.15.22, for example)
    * You are disconnected from DHCP server
    * Check cables. Wall outlets.
    * Check that NIC is not disabled in device manager.
    * Look at other end of the cable.
* Check the exam tip on 885
* Diagnosing physical problems.
    * key clue: "No server found"
    * Check lights
    * Check the NIC
        * Loopback test
    * Cable testing (RARE)

