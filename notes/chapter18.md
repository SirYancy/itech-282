---
layout: default
title: Chapter 18 - Essentials of Networking
nav_order: 10
permalink: /chapter-18
mathjax: true
---

Chapter 18 - Essentials of Networking
=====================================

Networking is a critical component to almost all computing

* Your computer is the *local host*.
* You access resources on a *remote host*
* A *host* is any computer connected to a network.
* Each networked host has a *role*.
* A *Web server* stores files that make up a Web site
* There are lots of different Web server software (Apache, etc)
* You use a *web browser* to ask the web server to share files.
* Since you are asking for the web page, you role is *client*.
* Since the remote hose is serving, it is the *server*.
* Same with things like YouTube.
* Even off the Internet, you can have a print server, for example
* Also *file server*, *mail server*. Example roles.
* Anything that can be shared over a network is called a *resource*.
* Networks need:
    * Something that defines and standardizes the design and operation of cabling, network cards, and interconnection of computers.
    * An addressing method that enables clients to find servers and enables servers to send data to clients, no matter the size of network
    * Some method of sharing resources and accessing those shared resources.

## Historical/Conceptual

* Three big questions
    1. How will each computer be identified?
    1. If two or more computers want to talk at the same time, how do you ensure that all conversations are understood?
    1. What kind of wire? What gauge? How many wires? Which wires do what? How long can cable be? Connectors?
* Both clients and servers need *network interface controllers* NIC
* The NIC also breaks files into smaller data units to send across network and reassembles them at the other end.

## Frames and NICs

* Data is moved in chunks called *frames*.
* NICs create and process frames.
* (note there is a difference between packets and frames)
* Every NIC has a unique *media access control (MAC) address*.
* This is a binary number.
* Each MAC is 48 bits long, which means 281 *trillion* MAC addresses.
* We usually shorthand MAC addresses to *hex*
* So it's usually 12 hex characters.
* They are burned into the card.
* Each fram contains 
    * the MAC address of dest NIC
    * MAC of source NIC
    * the data itself
    * CRC data to verify the data
* only one hardware protocol to handle this dominates the entire industry: Ethernet.

## Ethernet

* Over the years (since the 70s) Ethernet has gone through many imporvements called *flavors*.
* All flavors are, for the most part, compatible.
* Most networks employ one of these speeds:
    * 10BaseT
    * 100BaseT
    * 1000BaseT
* All three techs use *star bus* topology
* All connect via unshielded twisted pair (UTP) cables

### Star Bus

* It's a sort of hybrid topology.
* Central box *switch* is common point of connection for network devices.
* Early Ethernet networks used a *hub*, but these have been replaced by *switches*. Still on the exam.
* Hubs and swithces look the same, and do the same job.
    * take data and repeat it out across the network
* Hubs were dumb, and just broadcast to all connected devices.
* Switches memorize MACs and send to the correct device.
* Connection between computer and switch is a *segment*.
* Segments are usually 100 meters or less.
* The star bus means that any segment can be cut or go down, and network survives.

### UTP

* The predominant cabling system today.
* Many types.
* Uses AWG 22-26 guagues wire, twisted into color-coded pairs.
* Each wire is individually insulated and encased in  common jacket.
* Cat level chart in text on page 809
* Typically use 5e, 6, or 6a
* STP is rare and not used much because it's only necessary in places with lots of electircal interference.

### Ethernet with TP

* different levels need a specific CAT or higher.
* All use *RJ (registered jack)* invented by Ma Bell.
* RJ-11 is for your landline telephone
* RJ-45 is for Ethernet.
* RJ-11 connectors are used for telephone-based internet connections (we'll see this chap 21) DSL? I think?
* RJ-45 has connections for up to 4 pairs.
* Plenum wiring is important in offices. PVC gives off noxious fumes when burned
    * Plenum wiring uses flame retardant jacket. But it's 3-5 times more expensive. It's code for offices, though.
* Two standards for how they connect in the RJ-45. It doesn't matter which, but you should pick one and stick with it.

### Alternative Connections

* Fiber Optic
    * Immunite to electrical problems like lightning or short circuits.
    * signal travels farther (2000 meters)
    * Use 62.5/125 multimode fiber optic cable.
    * most require two cables. It's only half duplex.
    * LC connectors support both cables.
    * Use LEDs to transmit light
    * *multimode* transmits multiple signals at the same time at different reflection angles. used for relatively short distances
    * If they use laser light, it's usually *single-mode* cabling.
    * This is very high transfer rates over long distances.
* Coaxial
    * Coax lives on for cable modems and satellite connections.
    * Rated using RG name. You need to know 2
        * RG-59 and RG-6
    * Two connectors: BNC and F-type.

## Implementing Ethernet

* Common implementations of star bus.
* Typical LAN
    * *local area network*
    * A group of computers close to each other. (almost always)
    * They can all hear each other
    * A group connected by switches is called a *broadcast domain*
    * small office/home office (SOHO)
    * Most common way to set up is using *Wi-Fi*. (chapter 20)
    * Another option is *Ethernet over Power*.
    * Note: a *bridge* is something that connects dissimilar technologies
    * EoP can be good in weird places where wires cant reach.
* Structured Cabling
    * Important to note, that the real object of A+ is to be able to do basic troubleshooting and to communicate with cable installers, not necessarily to run your own cable.
    * Star networks aren't actually all that star shaped.
    * You don't really want to put your switch in the middle of the room and run cables to all the computers in the room.
    * You start with the *telecommunications room*.
    * Cables run horizontally from there.
    * Each horizontal cable is a *run*.
    * In most networks, this run is Cat 5e or better UTP
    * ANSI/TIA says all horizontal cabling should be solid core
    * Telecommunications Room
        * equipment racks are 19 inches wide. 2-3 ft high bolted to a wall, or a floor to ceiling model.
        * All sorts of equipment. Switches, servers, UPS, etc
        * All rack-mounted equipment uses high called a *U*. 1.75 inches.
        * Devices can be some number of U.
        * *patch panel* is where you connect permanent cables on the back (to avoid moving them a lot)
        * patch panels use a connector called a 110 block (110-punchdown block)
        * patch panels have room for labels. (there are standards, but not many people follow them)
