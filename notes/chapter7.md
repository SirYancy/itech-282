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
* Today, it's not an issue. A 12-v rail can push 70 amps or more.

### ATX12V 2.0

* Standardized the 24-pin connector
* Requires two 12-v rails for power rated higher than 230 W.
* Dropped the AUX and requires SATA for hard drives
* There are a couple ways that they maintain backward compatibility with old 20-pin power connector
* Some Motherboards want an 8 pin connector for CPU.
* These are sometimes splitable to a P4 connector and the other four pins.
* Also of note are the PCIe power connectors (6-pin)
    * There are sometimes 6 and 9 pin PCIe connectors. Sometimes, you need to use two
* Check the [SIM](http://totalsem.com/100x)

### Niche Market PSU form factors

* Briefly, Mini-ITX, MicroATX, TFX12V, SFX12V

### Active PFC

* Check the water metaphor in the text.
* Harmonics (humming) is generated by the way the PSU takes power from the wall socket
* It can damage the PSU. Enough harmonics-generating devies, can damage the power supplier's equipment.
* *Active Power Factor Correction* is extra circuitry that smooths out the power before going to main PSU circuits
* Eliminates harmonics.
* Never buy a PSU that doesn't have Active PFC

## Wattage Requirements

* Hard drives might want 15 W of power when being accessed.
* An i7-4790K at peak load uses 151 W of power.
* Know the total wattage of a system to judge whether PSU is sufficient
* Also, make sure that the PSU can power all the different *kinds* of devices.
* **Important** Most devices require *full* wattage at system start.
    * So you might have a paperweight that looks like a PC
* If you plug in a device and the system doesn't boot, then unplug the device and it does? 
    * Power Supply is the culprit
* Note: It is possible that a system might still run if at low wattage. But at reduced performance.
* No PSU is 100% efficient. Byproduct?
* ATX12V 2.0 requires 70%, but some PSUs are 80% or more.
    * Called 80+ or *80 Plus*
* 1001 does not require you to know the precise wattage requirements of a PC, but you will want to know something about this as a tech. Especially when building a new system.
* What happens if you install a PSU that can provide more wattage than you need?
    * Do you waste power?
* Buying an efficient, high-wattage PSU has two benefits:
    1. running at less than 100% load extends life
    1. Gives you lots of room to install new devices.
* Get more wattage than you need, as all PSUs degrade over time.
* Use at least 500 W.

# Installing and maintaining

## Installing

* Mounting a power supply usually four standard screws in the back of the case.
* Some considerations:
    * ATX PSU is *never off* as long as it's plugged in.
    * It's always supplying 5V to the mobo
    * So always unplug the system.
    * If you must leave it plugged in, use the hard switch.
* A trick: If you haven't installed in a case and have no power button, you can short the two pins to start the system.
* Before connecting HDDs, etc, plug in Mobo and GPU. See if it boots.
* Then plug in everything else.

## Cooling

* PSU has a fan. If for some reason, the computer starts and is strangely quiet, it might be a dead PSU fan.
* Sometimes the PSU has its own regulators on fans.
* Most cases have fans too.
* Where to plug in case fans?
* Some fans have molex connectors
* These days, there are usually 3-pin connectors directly to mobo
* Adapters also exist to molex

## Maintaining Airflow

* Running a system with the side open?
* A closed case creates airflow
* hot air rises, cold air goes down.
* Keep expansion bays closed.

## Reducing fan noise

* Options:
    * Manual adjusters on fans
    * Larger fans
    * "quiet" fans
    * Some mobos have software to control fan speed
* Larger fans spin slower
* quiet fans with ball bearings
* There's also CMOS settings for fans.

# Troubleshooting

* Two deaths:
    * Sudden
    * slowly over time
* If the PC doesn't turn on, check the wall voltage *first*
* Then check the PSU, voltage to the mobo, etc
* If any voltages are not correct, just replace. The soldering iron is not worth it.

## No mobo?

* ATX tester

## Switches

* If the power switch is broken (behind the power button), try shorting the soft power jumpers again.

## The Slow Death

* *Intermittent* problems.
    * PSU
* PSUs die more often than any other component except moving parts

## Fuses and Fire

* If the fuse pops, do not be tempted to go inside.
* Keep a fire extinguisher nearby
* C-Class fire extinguisher (ABC is fine)

## Modular PSUs (Not on exam)

* They are awesome.
