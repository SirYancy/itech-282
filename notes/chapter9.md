---
layout: default
title: Chapter 9 - Implementing Mass Storage
nav_order: 9
permalink: /chapter-9
mathjax: true
---

Chapter 9 - Implementing Mass Storage
=====================================

# Historical/Conceptual

* After installing a hard drive. What next?
* It must be *partitioned* and *formatted*.
* Partitioning is dividing the subdividing the physical drive into units called *partitions*
* Formatting is installing a *file system*.

## Partitions

* Magnetic hard drives have *sectors*
    * Old ones had 512-byte sectors. Newer ones have 4096-byte *advanced format* sectors.
* SSDs come with hundreds of millions of 4096-byte *pages*. A group of pages is a *block* (usually 128 pages per)
* Note that CPU and OS never talk to these structures.
* The controller on the HDD or SSD uses *logical block addressing*.
* This represents all the blocks as a number starting at LBA0.
* That's how the OS interacts.
* The user doesn't see any of this. We are presented with files and folders.

# 1002

* Windows
* Three types: MBR, dynamic, and GUID partition table (GPT)
* MBR and GPT are *basic disks*
* Dynamic is a *dynamic disk*.

## Master Boot Record

* The first sector of an MBR drive is the *master boot record* itself.
* This is what the BIOS looks for when it first boots up.
* The MBR contains the *partition table*.
* An MBR partition table supports 4 partitions.
* MBR supports two types of partitions: primary and extended
* Primary support bootable OS
* Extended are not bootable.
* You can have up to 4 primaries, or 3 primaries and one extended.

### Primary and multiple OS

* primary parts are assigned drive letters in Windows.
* Usually the first letter is C:
* After that D through Z are available.
* Mention Grand Unified Bootloader (GRUB)

### Extended partitions

* Extended partitions overcome the 4 partition limit
* These can contain mulitple *logical drives*
* The only thing that makes them different from primary partitions is that they all exist on the same extended partition.

## Dynamic Disks

* Windows 2000
* *dynamic storage partitio9ning* or *dynamic disks*.
* a drive structure created with this is a *volume*.
* It's still a partition, but it has added features.
* Dynamic disks can be as many volumes as you want.
* You can create (in software) new drive structures.
* ie RAID, spanned volumes, stripes, mirrors.
* Spanned volumes use unoccupied space across multiple drives to create one volume

## GUID partition table

* It's a lot like MBR except:
    * GPT is limited to 128 partitions
    * MBR is limited to 2.2 TB, but not GPT (it's really large)

## other partition types

* *hidden partitions*
* *swap partitions*


# Formatting

* Windows
    * FAT32
        * Fragmentation
    * NTFS

# Partitioning, Formatting, and Pooling

* bootable media
    * Boot device, boot disc
    * Install media for an OS
    * `.iso` files
* Partitioning and formatting with install media
    * Installing windows
    * There is a lab in ucertify to go through this process
* Disk management
    * Go through options for disk management

# Maintaining and Troubleshooting

* Maintenance
    * Error Checking
    * chkdsk, fsck, error checking, etc
    * Defragmentation
    * Disk cleanup
