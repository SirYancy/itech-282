---
layout: default
title: Chapter 10 - Essential Peripherals
nav_order: 8
permalink: /chapter-10
---

Chapter 10 - Essential Peripherals
==================================

* What is the purpose of peripherals?

## Supporting Common Ports

* Devices are not just devices. They are also interfaces and *ports*

### Serial Ports

* Oldie but goodie: (Recommended Standard) RS-232 and DB-9 connector.
* RS-232 refers to the standard. DB-9 is the connector

### USB Ports

* *Universal Serial Bus*
* This is a big one

#### Understanding USB

* *USB host controller* is normally built into the chipset
* It's the interface between the system and all of the USB devices
* Connected to this is the *USB root hub*.
* Text has a diagram of the relationship.
* A host controller supports up to 127 USB devices.
    * Though, this is unpractical for other limiting reasons
    * i.e. the AMD X370 chipset actually only supports 16 ports.
    * Few Mobo manufacturers are going to even include that many ports
* Host controller issues commands and supplies power to all connected usb devices.
* HC is *upstream* and controls all devices *downstream*.
* HC is shared by all devices. So power and speed are reduced with each new device.

#### USB Standards and Compatibility

* USB revisions:
    * USB 1.1 had two speeds: *low-speed* at 1.5 Mbps (keyboards, mice) and *full-speed* up to 12 Mbps
    * USB 2.0 has *Hi-Speed* at 480 Mbps
    * USB 3.0 can do 5 Gbps, marketed as *SuperSpeed USB*.
    * USB 3.1 can do 10 Gbps. Marketed as *SuperSpeed USB 10 Gbps*.

| Name                   | Standard | Max Speed | Common Usage                                                              |
| -                      | -        | -         | -                                                                         |
| Low-Speed USB          | USB 1.1  | 1.5 Mbps  | Keyboards, Mice                                                           |
| Full-Speed USB         | USB 1.1  | 12 Mbps   | Headphones, Bluetooth Devices                                             |
| Hi-Speed USB           | USB 2.0  | 480 Mbps  | Webcams, card scanners, older wireless adapters, older flash media drives |
| SuperSpeed USB         | USB 3.0  | 5 Gbps    | Flash-media drives, external storage, current wireless adapters           |
| SuperSpeed USB 10 Gbps | USB 3.1  | 10 Gbps   | Flash-media drives, external storage, networking                          |

* 2.0 is backward comopat with 1.1.
* 3.0/3.1 is compat with 2.0. 
* But to use full capability, use appropriate devices with appropriate ports
* *USB expansion cards* can add SuperSpeed USB to a mobo that doesn't have it.
* 1.1 and 2.0 Host controllers and ports share the same root hub (see diagram)
* 3.0 and 3.1 both use separate host controllers.

#### USB Cables and Connectors

* Different type connectors. A and B mini-A, mini-B etc
* A goes upstream. B goes downstream
* Pay attention to terms.

| USB Standard | Port Color |
| -            | -          |
| 1.1          | White      |
| 2.0          | Black      |
| 3.0          | Blue       |
| 3.1          | Teal       |

* The joke about three tries to connect USB-A
    * Up position, Down position, superposition (up repeated)
* USB-C supposedly replaces both A and B
* USB-C uses 24 pins, can be inserted either way. Is compatible with thunderbolt. Is replacing micro-USB as dominant for devices
* Cable lengths: 
    * 1.1-2.0 limit 5 meters.
    * 3.0/3.1 does not list a length, but. 2 meters is a reasonable length to avoid interference.

#### USB Hubs

* HC supports 127 devices.
* If you don't have enough ports, what do you do?
* Add another host controller (expansion card)
* Or: Add a USB hub to an existing port.
* Sometimes they are even built into existing peripherals (monitors, keyboards, etc)
* Consider using powered hubs

#### USB Configuration

* 
