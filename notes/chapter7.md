---
layout: default
title: Chapter 7 - Power Supplies
nav_order: 6
permalink: /chapter-7
mathjax: true
---

Chapter 7 - Power Supplies
==========================

* Computers need electricity
* They have a *power supply unit* (PSU)
* It is important to learn a little bit about electricity to handle this topic
* PSUs are classified by A+ as a *Field Replaceable Unit* (FRU)

## Historical/Conceptual

### Electricity

* Electicity is the flow of electrons
* All matter allows *some* flow
* A common metaphor is water flowing through pipes
* You know that when you turn on the faucet, water will come out at a more or less constant rate
* This is the same as with electricity
* It is generated and then pushed to your house under pressure through wires
* You pay for reliability, electrical pressure, and what electricity you use

Voltage
: pressure of electrons in the wire. Measured in *volts* (V)

Amperage
: Amount of electrons moving past a point in the wire. Called *current* or *amperage*. Measured in *amperes*, *amps* or *(A)*

*Wattage*
: How much amps and volts a device needs. *Watts*, *(W)*.

*Resistance*
: resistance to flow of electrons. Measured in *ohms* (&#8486;)

Relationship: $V \times A = W$

* A particular thickness of wire only handles so much current at a time.
* Push too hard and it will overheat and break
* Same as with an overpressurized pipe
* All wires have an amperage rating
* If you push 30 amps through a 20 amp rated wire, it will break. Electrons will find the shortest path to ground. Even if it's through you
* In buildings, we use circuit breakers and ground wires
* Think about how circuit breakers work
* A ground wire also provides a path for electrons to flow back to ground.
* Back in the day, people used fuses
* We don't use fuses anymore in houses, but we do still use them in other places
    * Cars
    * and Computer Power Supplies!
* Once a PSU's fuse is broken it cannot be replaced, but at least it didn't destroy your mobo
* **Important!** an outlet for a PC *must* have a ground wire
* Electricity comes in two flavors. 
  * *direct current (DC)*, all electrons flow in same direction
  * *alternating current (AC)*, flow alternates back and forth
* All electronics use DC, but all outlets supply AC. Why?

# Powering the PC

* What does a PSU do?
* Converts high voltage AC power to low-voltage DC
* First, you need a good supply of AC power.
* Second, you need to convert it to the correct voltage and amperage for the mobo and peripherals
* Last, you need to somehow control the byproduct of all that electricity usage: heat

## Supplying AC

* You need standard AC power supplied steadily. You also need protection against accidental surges, blurps, and whatever
* Computers typically use a standard *IEC-320* connector to plug into the wall.
* In the US, AC is between 110 and 120 V (~115 VAC).
* Rest of the world typically uses 220-240 VAC. 
* There are PSUs with *dual voltage options*
* Some have a switch. Some are auto switching. Som are fixed. *if you travel, you need to know what power supplies you're using*
* Image in text: hard on/off switch, 115/230 switch, IEC-320 connector
* IEC-320 has three holes. Hot, neutral, and ground
    * Hot wire has electrical voltag
    * Neutral carries no voltage, it's like a drain
    * Ground lets excess electricity return safely to the ground.
* When testing AC power, check three things:
    * Hot outputs 115V,
    * Neutral connects to ground (0V)
    * and ground connects to ground (0V)
* Let's play with the multimeter

### Other Considerations

* Some computers use an AC Adapter. (phones and such)
* When checking an AC adapter, check three things: voltage, amperage, and polarity

## Supplying DC

* After you know you have good AC
* PSU starts converting public utility voltage into DC voltages
    * 3.3, 5.0, and 12.0
* Most common size PSU is 150mm x 140mm x 86mm
* Possible typo in Exam Objectives page 10 on voltages
* The PC uses 12V to power motors
* 3.3 and 5V for electronics.
* PSU comes with standard connectors for MB and interior devices

### Motherboard

* 20- or 24-pin *PI power connector*
* Some motherboards may require extra 4- 6- or 8- pin connectors

### Peripherals: Molex, Mini, and SATA

* Lots of things needs power.
* Usually 3 other types of power connectors

#### Molex

* Supplies 5- and 12-V for fans and older drives. It has notches called *chamfers* that guide its installation. 
* You really have to push on these. Still, you can beat them and install it upside down
* *always check!*

#### Mini

* Some PSUs still support *mini* connector or *Berg* connector
* Was standard for 3.5 in floppy. Some devices still need them.

#### SATA

* Serial ATA drives need a 15-pin *SATA power connector*
* supports hot-swapping
* 3.3, 5, and 12 V
* 3.3V pins are not currently in use for any devices (future proofing)
* They are easy to install

#### Splitters and Adapters

* It could happen that you don't have enough connectors
* You can get splitters to create more connections
* There are also Molex to SATA adapters and vice versa

### ATX

* Two main distinguishing features:
    * Motherboard power connector
        * 20-pin PI connector
        * At least 2 other connectors with 2 or more Molex or Mini connectors
    * soft power
        * At all times, ATX hav 5V running to Mobo. Always "on"
        * The button isn't *really* a power switch.
        * It just sends a signal. This is "soft" power
* Two main reasons for soft power
    * Prevents people from turning off the computer before it's done shutting down.
    * Enables things like power-saving mode and sleep states
    * CMOS settings have more.
* Let's look at updates that have happened to ATX power

#### ATX12V 1.3

* 2003
* Introduced a 4-pin power connector called *P4*. Adds more 12V power.
* Also introduced the 6-pin auxiliary connector *AUX* to supply extra 3.3 and 5V.
* There were problems. Bad enforcement of standard meant you had to be very careful to buy the right PSU.

#### EPS12V

* Mostly for servers. Had  lots of additional connectors and made some interesting advances.
* Main contriubted thing was the concept of *rails*

#### Rails

* All power comes from a transformer that converts AC to DC and splits it between primary DC voltage rails
* Each rail has a maximum amount of power it can supply.
* Usually, this is not a big deal, but big PCs sometimes need more power
* So they started adding multiple rails.
* They had a tough time balancing current between rails until about 2008
* Today, 
