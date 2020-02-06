---
layout: default
title: Chapter 24 - Understanding Mobile Devices
nav_order: 24 
permalink: /chapter-24
mathjax: true
---

Chapter 24 - Understanding Mobile Devices
=========================================

* Qualities of mobile devices
    * Lightweight (2lb or less)
    * Small (hand or pocket sized)
    * touch or stylus interface
    * sealed unit lacking replaceable parts
    * non-desktop OS (special operating systems)

* Essentially 2 operating systems
    * Apple iOS
    * Google Android

# 1001

## Device Variants

* Smartphones
    * PDA was predecessors (1990s)
    * Blackberry deserves a mention
    * iPhone was the one that really started the revolution
        * multi-touch interface
        * standardized API
        * tight consolidation of network connectivity
        * synchronization and distribution tools (app stores, data sync)
    * It's important that infrastructure be fast, robust, and secure
    * Repairing them is hard.
* Tablets
    * Generally only 802.11 wifi
    * Very large spectrum of capabilities
* Purpose-built devices
    * MP3 players are an example.
    * A+ wants you to know about ereaders and GS devices.
    * e-readers
        * for reading books
        * Have a grayscale low-power e-paper interface.
        * Typcally have touchscreens these days (after hardware buttons)
        * Amazon Kindle Paperwhite is an important example.
        * Battery life measured in days or weeks
        * most other devices have available kindle app
* Wearable Technology
    * Very small
    * small interfaces
    * Light OS (only a subset of typical mobile OS)
    * Limited hardware (accelerometer for step counting)
    * Pairs with a host device
    * Comptia lists three: smartwatches, fitness monitors, VR/AR headets
    * Smart Watches
        * Streamlines certain common smartphone tasks: check messages, weather, music playback, fitness montioring
    * Fitness monitors
        * Count steps with accelerometer
        * register heart rate
        * GPS to track exercise
        * Two form factors: clip to you, wear on your wrist
    * VR/AR headset
        * VOIP headsets
        * VR/AR
        * AR allows you to add elements to the world you are already in.
        * Look at the NASA AR apps
        * Google Glass bears mentioning
        * Other specialized AR headsets exist

## Mobile Hardware Features

* Screen technologies
    * Most tablets use LCD of some sort
    * Twisted Nematic (low-end) or in-plane switching (high end)
    * Smaller devices usually use OLED or AMOLED
        * Both of these do *not* have a back light. They can show true black and use less electricity
* Cameras
    * All devices have cameras. Some are even better than dedicated digital cameras
    * Include things like HDR, light compensation, etc
    * Lots of apps to support
* Microphones
    * At least one microphone, obviously
* Digitizers
    * This is the component that gives you the "touch".
    * your finger touches a grid of sensors and it informs the OS where it was touched.
    * Configuration is mentiond in the objectives, but it's not really a thing.
* GPS
    * ALmost all devices have GPS.
    * Location services track you via GPS, cellular, and wifi connections
    * Navigation
    * Find my phone
    * Waze, google maps, etc
    * Standalone GPS Devices
        * Clip to a dashboard.
        * Variants for all sorts of devices (boats, bikes, airplanes, etc)
        * Sometimes have features that smartphones don't.
    * Location Tracking and Privacy
        * Geotracking is a big deal

# 1002

## Mobile OS

* Development Models
    * Closed Source
        * Make something. Don't tell anyone how you did it.
        * Vendor-specific and proprietary
    * Open Source
        * Release the instructions for how to make something
    * Advantages and disadvantages of both options
    * Android vs iOS
* iOS
    * Closed source model.
    * Strictly controlled
    * hardware, OS, developer tools, app deployment platform are all Apple controlled
    * Exceptions to this exist (*line-of-business* apps)
* Android
    * Oversimplification: Android and iOS are opposites
    * open-sourced
    * based on another open-sourced platform (Linux!)
    * Device manufacturers customize and alter it
    * App stores are various
    * Looser controls
    * Easier to install arbitrary apps

### Mobile OS Features

* User Interfaces
    * All have GUI
    * Pinching zooming
    * swiping
    * ioS has the same GUI with a few customization features (folders and such)
    * Android utilizes *launchers* that can be swapped out.
    * Often device has accelerometer or gyroscope to maintain screen orientation
* Wi-Fi Calling
    * Support for cellular calling is assumed
    * However, you can also call via wifi
    * Useful if there's bad cell reception, but good Wi-Fi
* Virtual Assistants
    * Lots of things to talk about here
* Software Development Kits
    * Apple and Microsoft have strict testing that must be passed before releasing an app
    * Android lets any old joker release and distribute an app!
* Emergency Capabilities
    * *emergency notification* feature
    * Receive broadcasts from EAS
    * AMBER Alerts
    * E911
* Mobile Payment Service
    * NFC features
* Airplane Mode
* Radio Firmware
    * Usually both 802.11 and Bluetooth
* PRL, PRI, and Baseband Updates
    * *Preferred Roaming List*
    * CMDA devices can get *product release instruction (PRI)* updates
        * These affect things like GPS, cellular hardware, and messaging
