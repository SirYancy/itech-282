---
layout: default
title: Chapter 10 - Essential Peripherals
nav_order: 8
permalink: /chapter-10
mathjax: true
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

### FireWire Ports

* FireWire IEEE 1394
* Final version of standard (IEEE 1394b) could run 800 Mbps.
* Camcorders and external storage.
* Becoming rare.

### Thunderbolt

* Thunderbolt ports tap the PCIe bus.
* Supports up to six external peripherals
* A thunderbolt card can add ports.
* Supports up to a single 4K video monitor as well as audio.
* Data storage as well.
* TB 1 and 2 used Mini DisplayPort (mDP)
* TB 3 uses USB Type-C
* Can use either copper or fiber cables. 
* copper can be 3 meters.
* Fiber can be 60 meters.
* USB and TB use same connector, but are not compatible.
    * Look for the logos
* TB 1 at full duplex ran 10 Gbps.
* TB 2 is 20 Gbps
* 3 is 40 Gbps at half the power consume.

### General Port Issues

* Problems:
    * First, find out if port issue or device issue
    * How?
* If port is not working
    * Check if port is turned off (system settings/CMOS)
    * Windows Device Manager
    * If you don't see a port and you're sure it's enabled, it's probably a physical problem.

### Common Peripherals

* Keyboards
    * Built-in drivers control most keyboards
    * special keyboards with cool features might need special drivers
    * Most connect via USB, but PS/2 is having a resurgence.
    * You can set many settings in Keyboard Control Panel applet.
    * QWERTY keyboards are standard
    * Windows and Linux support ctrl and alt
    * Apple has three modifier keys: CONTROL OPTION COMMAND
    * If you have a windows keyboard on apple machine, you may have to remap the windows key
    * Keyboard failures usually result of three issues: spills, physical damage, dirt
        * Spills: maybe if you unplug it quickly enough Maybe not worth it. Laptops are a problem.
        * Damage: usually resilient, but can be broken.
        * Dirt: Clean with damp cloth or a bit of isopropyl.
        * You can use compressed air.
        * Keep them clean, or buy a new one.
* Pointing Devices
    * Mice and Touchpads
    * Apple has multi-touch gestures
    * Pointing devices need little maintenance.
    * Sometimes, if it behaves badly, try cleaning the optics (rare)
* Biometric Devices
    * Lots of authentication methods
    * iris, face, head image, fingerprint.
    * macOS and Windows 10 have support for biometrics
    * Windows Hello
    * Espeically common with smartphones (apple and Android)
    * Biometrics is also used for recognition
        * Voice recognition software: Siri, Cortana, Google.
        * Google Docs also has voice recognition.
    * Installation is always the same
        * Install device
        * Register identity using setup routine
        * COnfigure software to tell it what to do when it recognizes you.
* Smart Card Readers
    * Added security by using non-password-protection (FIDO)
    * RFID
* Barcode/QR Scanners
    * for scanning UPCS or Quick Response COdes
    * pen scanners and gun scanners
* Touch Screens
    * Either built-in or peripheral
    * Smartphones, fitness monitors, POS, tablets, e-readers, etc
    * standalones can be thought of as monitors with a built in mouse (it'll usually have another usb cable)
    * Windows has a control panel applet for configuring these
    * Windows also has a tablet mode
* KVM Switches
    * Keyboard, Video, Mouse
    * Installing is typically easy.
* Game controllers joystics
    * Used primarily for video games
    * Especially games that were originally designed for consoles
    * joysticks used to be essential equipment. :(
    * Pretty much all of them use the USB these days
    * Some are wireless
    * You might need drivers or adapters.
* Digitizers
    * pen tablet
    * Wacom tablets are popular
    * Mostly via usb
* Multimedia Devices
    * Digital Cameras
        * Storage media might be Secure Digital (SD) cards
        * Connection via usb, or other digital media readers
    * Webcams
        * Typically marketed the same as video camers, ie. terms like 720p, HD, 4K
        * most common are 1080p HD. Integrated in laptops, usually like 720p
        * Often built-in mic
    * Sound Devices
        * To record analog sound, you must use a process called *sampling*.
        * Sampling rate is measured in cycles per second (KHz)
        * Range from 11 KHz to 192 KHz.
        * loudness (aplitude), pitch (frequency), qualities that differentiate between instruments (timbre)
        * bit depth of the sample is how many characteristics are translated into digital
        * 8-bit sample captures 
        * $ 2^8 = 256 $ characteristics. It would sound like a recording of a recording. Flat. Thin
        * 16-bit sample would be $ 2^{16} = 65,536 $ characteristics. It's going to sound a lot better
        * Tracks (mono stereo)
        * CD quality is 44 KHz and 16-bit depth.
        * Book plugs Audacity
        * Sound cards are a thing. Usually referred to whatever sound hardware is installed. Either built-in or add-on
        * Formats
            * PCM *Pulse code modulation* is the original. Used for first digital telephone lines
            * WAV is actually PCM. Faithful storage of sound. But large files
            * 4 minutes at CD quality is 40 MB
            * Human ear can't really hear all that detail though
            * Then there are compressor/decompressor (codec) algorithms to compress out some of that stuff
            * Fraunhoffer MPEG-1 Layer 3 codec (MP3)
            * Advanced Audio Encoding (AAC) is used by YouTube, Apple, iPhone etc.
            * Also streaming media, which broadcast, played, and discarded.
            * *musical instrument digital interface* MIDI. Store large amounts of data in tiny files using onboard instruments of sound card (advantages/disadvantages)
        * Speaker support
            * Built in with all mobos
            * Sometimes up to 5 or more channels
            * Sometimes you might use a subwoofer
            * Dolby Digital (DTS)
            * Dolby 2.1 supports two satellites and a sub
            * 5.1 has 5 satellites and a sub
        * Jacks
            * 3 jacks: speaker, mic, line in
            * Color codes
            * speaker is green
            * line in is blue
            * mic is pink
            * Others
            * main speaker out
            * line out
            * line in
            * rear out
            * analog/digital out
            * microphone
            * Also might have *Sony/Philips Digital Interface (S/PDIF)* Connects directly into a 5.1 system
