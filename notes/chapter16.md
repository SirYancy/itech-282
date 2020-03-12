---
layout: default
title: Chapter 16 - Troubleshooting Operating Systems
nav_order: 16
permalink: /chapter-13
mathjax: true
---

Chapter 16 - Troubleshooting Operating Systems
==============================================

* Windows is a *heterogeneous ecosystem*
    * This means that it can be quite a challenge locating and diagnosing errors
* Macintosh is more *homogeneous*
    * It's a bit easier because of strictly controlled software
* Linux production machines (servers?) generally aren't super complex and work well. That said, linux workstations are becoming more common and can be difficult to diagnose for many of the same Windows reasons

# Failure to Boot

* Hardware or software?
    * Hard drive needs connection and power
    * CMOS needs to be configured correctly
    * If POST completes and boot fails at this point, we have other issues.

## Failure to Boot: Hardware or config

* Customer calls and says, "My PC won't boot" or "My computer is dead."
* Questions to ask:
    * What displays on the screen when you press the power?
    * What do you hear after you press the power button?
    * Is the PC plugged in?
    * Do you smell anything weird?
* Make sure everything is plugged in
* If new: it could be burn-in
* weird smell? Something fried
* Try replacing with known-good components: RAM, PSU, CPU, HDD, Mobo
* If "no boot device detected" and computer used to boot, it *could* just be that it tried to boot off a thumb drive

## Failure to boot: Windows Edition

* Two boot files risk corruption
* bottmgr and bcd.
* They can be fixed with bcdedit
* This can be accessed through *Windows Recovery Environment*
* Create Windows install media (if you don't already have it) and boot off that.
* *Windows Preinstallation Environment* Windows PE
* Tools called *Windows Recovery Environment*

### Windows RE

* In Windows 7, you can access with 3 ways
    * Install media
    * Repair Your Computer from advanced boot menu (`F8`)
    * Create system repair disk or system image before you have problems.
* Windows 8+ creates a recovery drive on a 16 GB+ flash drive
    * Boot from that drive
        * This all assumes you can't get into Windows. You can get to WinRE from the control panel as well.
* In 10, you can download the installation media straight from MS website
* You can also boot from recovery drive.

### Using WinRE

* It looks different between 7, 8, 8.1, 10.
* But same options are there.
    * Startup repair
    * System restore
    * System Image Recovery
    * Windows Memory Diagnostic
    * Command Prompt
* With 8+, you might have to click around, but the same tools are there.
    * See screencaps in text (688)
* Startup repair fixes almost any boot problem. As long as the hard drive itself isn't fried
* Startup repair can automatically run if Windows detects a boot problem.
* System restore
    * This puts you back to a restore point
    * a time when the computer still worked
* System Image Recovery
    * Restore after catastrophe
    * Works especially well if you manage a lot of uniform systems.
    * Keep a default image on hand.
    * You can reimage a borked computer quick
* Windows Memory Diagnostic
    * bad RAM causes problems
        * BSoD
        * lockups
        * boot loops
    * Checks system RAM
