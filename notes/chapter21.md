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
