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
* 
