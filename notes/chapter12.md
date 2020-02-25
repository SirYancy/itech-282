---
layout: default
title: Chapter 12 - Windows Under the Hood
nav_order: 12
permalink: /chapter-12
mathjax: true
---

Chapter 12 - Windows Under the Hood
===================================

# The Registry

* Registry files are called *hives*.
* Stored in `\%SystemRoot%\System32\config` folder
* And each user account folder
* You do not want to access these files directly
* Instead, you use a set of applications to edit it.
* 1002 does not include an objective for the registry, but
* You should know it anyway.
* regedit
* You have five key components: *root keys*
* HKEY_CLASSES_ROOT
    * defines key class objects.
    * So it defines what to do with various class objects.
    * For example, jpg files
    * File associations and things like that.
* HKEY_CURRENT USER and HKEY_USERS
    * Since windows supports multiple users, these store multiple users (desktop backgrounds, etc)
    * Can you guess what each HKEY stores?
* HKEY_LOCAL_MACHINE
    * all data for system's non-user-specific config. Devies and programs and such
* HKEY_CURRENT_CONFIG
    * Used any time HKEY_LOCAL_MACHINE has more than one option (like if there are two monitors)

## What's it all for?

* Example in text about *World of Warcraft*
* Values in Registry entries have data types:
    * String value
    * Binary value
    * DWORD value (32 bits)
    * QWORD value (64 bits)
    * There are more, but these are the most common

## Manual edits

* This is a last resort. Usually your system will manage all of these things for you!
* ONLY DO THIS IF YOU NEED TO OR IF YOU KNOW WHAT YOU'RE DOING AND WHY.
* There are also command line tools like *regsvr32* and *reg*

# Boot Process

* Windows supports both BIOS and UEFI boot process.
* The first thing that happens is one of these things runs.
* What happens next depends on which one
    * BIOS: 
        * uses boot order to scan a hard drive for MBR. 
        * This will tell it to scan the partition table. 
        * Then load the boot sector. 
        * The boot sector points to the *bootmgr*.
        * In summary: BIOS looks for MBR, which finds the boot code to launch Windows
    * UEFI:
        * UEFI just runs the *bootmgr* directly.
* *Bootmgr* reads data from a *Boot Configuration Data* (BCD) file.
* It tells the system about various OS isntalled in the system.
* It also tells how to bootstrap them.
* Then once Windows is selected, it runs a program called `winload.exe`
* This sets you up to load the Windows kernel `ntoskrnl.exe`
* This loads the hardware abstraction layer, the registry, the drivers etc and then...
* Then Windows takes over


