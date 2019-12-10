---
layout: default
title: Chapter 21 - The Internet
nav_order: 13
permalink: /chapter-21
mathjax: true
---

Chapter 21 - The Internet
=========================

## How the Internet Works

* **Internet Tiers**
    * internet is broken into groups called *tiers*.
    * *Tier 1* is a small number of *Tier 1 providers*.
    * They own long-distance high-speed fiber optic networks called *backbones*
    * They span major cities. Not all Tier 1 networks hit all cities.
    * They must connect at special locations. *Network Access Points (NAPs)*
    * *Tier 2* providers are regional. They pay Tier 1 providers
    * *Tier 3* providers are even more regional. 
    * They connect to Tier 2 networks via *backbone routers*.
    * Imagine what happens when parts of the network go down?
* **TCP/IP** again
    * Provides the addressing scheme.
    * But it's more than that.
    * It provides a framework that is extensible
    * Using this barebones concept, you can create *TCP/IP services*.
    * But how do we get into it?
* **Internet Service Providers**
    * Tier 1 and 2 providers lease connections to ISPs.
    * You tap into an ISP to gain access to the Internet
    * ISPs come in all sizes
* **Concepts**
    * Need two things to connect.
        * Hardware (modem, cable, etc)
        * Software (protocols, applications, etc)
    * Once you establish a contract with ISP, they probably provide hardware
    * When you connect, what kind of server do you first contact to get on the Internet? (DHCP)
    * What is your router in your house called? (Default gateway)

## Connecting to the Internet

* Many ways to connect.

### Dial-up

* This is still kind of a thing.
* Still in the exam objectives
* You need two things (as usual)
    * Special hardware to dial up to the ISP (a modem or ISDN adapter)
    * Software to manage the connection
* **Modems**
    * Phone lines are analog
    * Computers are digital
    * The modem is the device that converts these signals back and forth.
    * [Modem Handshake](https://www.youtube.com/watch?v=vvr9AMWEU-c)
    * It allows computers to talk to each other via standard commercial telephone lines
    * stands for modulator/demodulator
    * Phone lines have a standard speed called *baud*
    * *baud* is 1 cycle per second
    * phone lines are limited to 2400 baud
    * Modems can actually smoosh many bits into a single baud.
    * 33.6 smooshes 14 bits into each baud $2400 \times 14 = 33.6 Kbps$
    * Note: Modems use Cat1 cables with RJ-11 connectors
    * There are external (USB) and internal (PCI) modems

## ISDN

* It's useful to know how phone networks work.
* YOu have your phone, which connects to a network interface box on your house
* This is connected to a central switch. There might be many of these central switches in a town
* These connect to each other via trunk lines
* Over time, these analog networks and switches were upgraded from analog to digital
* customers demanded higher bandwidth Internet access.
* Phone lines were supposed to be capped at 28.8 Kbps (though they did manage to squeeze out 56 Kbps)
* So how did they get the greater speeds?
* Make the whole phone system digital.
* *Integrated Services Digital Network* (ISDN) was born
* Two types of channels: Bearer (B) and Delta (D)
* Usually use two B and one D channel for 128 Kbps.
* Expensive to install.
* Need to typically be 18,000 ft from central office to have ISDN.
* Note: *primary rate interface (PRI)* uses twenty-three B channels to get 1.544 Mbps. This is called a T1 line.
* ISDN wall socket looks like RJ-45
* ISDN is becoming increasingly rare.

## DSL

* *Digital Subscriber Line*
* Uses a standard telephone line with special equipment.
* Creates and always-on internet connection.
* At the low-end, less than 1Mbps. Up to hundreds of Mbps
* Requires little setup for a user. Tech comes out and plugs stuff in.
* You can do it yourself.
* Need to be fairly close to the central office.
* Up to about 18,000 ft.

## Cable

* Uses TV cables to serve up speed.
* Typically faster than DSL
* Up to 1000 Mbps download speeds

## Fiber

* Lots of things have influenced FTTN and FTTP rollout. (Google Fiber among them)
* Difference between FTTN and FTTP
* Up to 1+ Gbps

## Wi-Fi

* Covered in detail in chapter 20

## Line-of-Sight Wireless

* In some remote areas, you can use high-powered directional attenas.
* Places like ski resorts
* To get higher speeds, you might use very high frequencies 24-GHz

## Cellular

* Several generations.
* 3G cellular is not great. Just under 10 Mbps download speeds
* We are currently in 4G and moving into 5G
* 4G incorporates the *Long Term Evolution (LTE)* technology.
* LTE is considered "true 4G" and has theoretical download speed of 1Gpbs and up speed of 100Mbps.
* LTE could theoretically replace wired networks. Using *wireless hotspots*.
    * Why haven't they?
* In addition to LAN and WAN, there are also WLAN and WWAN.
* A hotspot is a form of *tethering*.
* 5G specification calls for speeds of 20 Gbps

## Satellite

* Satellite connections require line of sight to satellite
* A satellite modem handles translation
* Coax runs from dish to satellite modem
* Some offerings feature 25 Mbps down and 3 Mbps up
* Downsides:
    * *satellite latency*
    * *fair access policies*

# Connection to the Internet

* Two options
    1. Connect a single computer to your Internet connection
    1. Connect a network of computers to your Internet connection
* Number 1 is easy, though there are steps that should be taken to be secure
* Number 2 is a bit more complex. You need a router.
* Loads of fine routers.
* Most have 4 ethernet ports and one or more Wi-Fi radios
* They use a tech called *Network Address Translation (NAT)*.
    * This presents all of the computers on the network as if they are the same machine.
    * It hides the entire network from the rest of the Internet.
    * NAT is a kind of a firewall in a sense.

## Basic Router Config

* Usually accessed via a web interface

* Changing the user name and password
    * You should always change the username and password of the router.
    * Usually fairly easy to find in some admin menu
* Setting Static IP addresses
    * Typically IP addresses are dynamically assigned via DHCP
    * But static IP addresses are possible (extra fees)
* Updating Firmware
    * Periodically, routers have firmware updates that need to be applied.
    * Mine needs one right now.
    * They have the possibility of bricking your router. (rare)

# Internet Application Protocols

* You need specific applications to do certain things on the Internet
* Each of these has a protocol and ports (what exactly are ports?) which you must know.
* The only ones you need:
    * World Wide Web (HTTP and HTTPS)
    * E-Mail (POP3, IMAP, SMTP)
    * Telnet
    * SSH
    * FTP/SFTP (SFTP is not in the exam objectives)
    * Remote Desktop Protocol (RDP)
    * VoIP (SIP) (not actually in exam objectives)
* Example: HTTPS
* Application protocols

| Application Protocol | Function                     | Port Number |
|----------------------+------------------------------+-------------|
| HTTP                 | Web Pages                    | 80          |
| HTTPS                | Secure Web Pages             | 443         |
| FTP                  | File transfer                | 20, 21      |
| SFTP                 | Secure file transfer         | 22          |
| IMAP                 | Incoming e-mail              | 143         |
| POP3                 | incoming e-mail              | 110         |
| SMTP                 | Outgoing e-mail              | 25          |
| Telnet               | Terminal Emulation           | 23          |
| SSH                  | Encrypted terminal emulation | 22          |
| RDP                  | Remote Desktop               | 3389        |
| SIP                  | Voice over IP                | 5060        |

* Utility Protocols

| Utility Protocol | Function                                 | Protocol | Port Number   |
|------------------+------------------------------------------+----------+---------------|
| DNS              | Allows use of DNS naming                 | UDP      | 53            |
| DHCP             | Automatic IP Addressing                  | UDP      | 67, 68        |
| LDAP             | Querying Directories                     | TCP      | 389           |
| SNMP             | Remote management of network devices     | UDP      | 161, 162      |
| SMB              | Windows naming/folder sharing; also CIFS | TCP      | 445           |
|                  |                                          | UDP      | 137, 138, 139 |
| AFP              | macOS file services                      | TCP      | 548           |
| SLP              | Services discovery Protocol              | TCP/UDP  | 427           |
| NetBIOS/NetBT    | NetBIOS over TCP/IP                      | TCP      | 137, 139      |
|                  |                                          | UDP      | 137, 138      |

# Internet of Things

* Important ones to know:
    * Thermostat
    * Light switches
    * Security Cameras
    * Door Locks
    * Digital Assistants
* 
