---
layout: default
title: Chapter 8 - Mass Storage Technologies
nav_order: 7
permalink: /chapter-8
---

Chapter 8 - Mass Storage Technologies
=====================================

* What's the most valuable part of a computer?

## Historical/Conceptual

### How Hard Drives Work

* Two main types
    * Traditional type with moving parts (HDD)
    * No moving parts (SSD)

### Magnetic Hard Drives

* Traditional *Hard Disk Drive (HDD)*
* individual disks called *platters*
* read/write heads on actuator arms controlled by a servo
* sealed case to prevent contamination
* Aluminum platters are coated with magnetic medium
* Two tiny heads service each platter
* Each head has a bit-sized *transducer*
* alternate names
    * magnetic hard drives
    * rotational drives
    * platter-based hard drives

### 1001

**Spindle Speed**

* spindle speed is measured in RPMs
* older drives used speeds of 3600 RPM.
* Some today reach 15,000 RPM
* Speed dictates read/write speed
* Most common speeds are 5400 and 7200
* high-performance drives are 10,000 and 15,0000
* faster hard drives have better performance but shorter lives.
    * Higher temps can reduce life by as much as 2 years (5 C)
* To mitigate heat is to install drive bay fans or have a more spacious case
* Things that can impede airflow:
    * ribbon cables
    * USB headers
    * a tiny case
    * dust and animal hair
* Mitigate by
    * Tying off cables
    * Adding fans
    * If the client wants a tiny case, encourage slower drives

#### Form Factors

* Standardized at 2.5-inch and 3.5 inch.
* Desktops can use either, but laptops use the smaller
* Form factor only dictates size

### Solid-state drives

* Consider issues with HDDs
* SSDs address some of these issues.
* Based on semiconductors and transistors that create electrical components with  no moving parts.
* Basically, they use flash memory chips.
* Flash technology is used in desktop and laptop hard drives, memory cards, cameras, USB thumb drives, phones
* Three form factors
    * 2.5 inch
    * mSATA
    * M.2
* mSATA and M.2 plug into specific slots
* modern mobos may have 2 or more M.2 slots.
* *NOTE* mSATA is on the way out, though may still be on the exam. M.2 is the winner.
* M.2 slots are keyed (B, M B+M, A, E) and these are not on the exam. 
* Chapter 10 talks more about non-volatile storage tech.
 
#### Cost

* SSDs can use *multi-level cell (MLC)* or *single-level cell (SLC)* technology
* *3D NAND* stacks cells vertically, to increase density
* Scattershot storage. Rules are opaque to OS

#### Performance Variables

Three essential metrics

* Read and write long sequences
* Read and write short sequences
* respond to requests.

The importance of these varies depending on need.

#### Sequential Read/Write performance

* *throughput* is the speed it can read/write long squences of data.
* Sequential read and sequential write are expressed in megabytes per second (MBps) (read is usually faster than write)
* Traditional HDDs top out at 200 MBps.
* SATA SSDs hit 600 MBps.
* NVMe SSDs can hit 2500 MBps. or faster
* This is important if the system frequently deals with large files.
* But not many systems do.

#### Random Read/Write Performance

* *random read*, *random write*, and *mixed random* performance are benchmarks that we are usually concerned with.
* How many times per second the drive can read or write small, fixed-sized chunks of data at random locations.
* Usually 4 kilobytes
* You'll see this as 4K read, 4K write, 4K Mixed
* Also expressed as *input/output operations per second (IOPS)* Though occasionally also as MBps
* Traditional HDD: 150 IOPS
* NVMe SSDs can hit *hundreds of thousands* of IOPS

#### Latency

* response time, access time, latency
* usually expressed as milliseconds (ms) or microseconds (&micro;s)
* low-latency is critical for file and database servers
* But it's not a big deal for typical users
* HDDs 20 ms
* SSDs under 1 ms
* Consider use cases
    * Typical user workstation (boot up time, file access)
    * video editor or large file server
* So weigh the options for exam purposes. But in the real world, don't worry too much unless you have a very demanding system.

### Hybrid Hard Drives

* HHDs
* ALso SSHDs
* Cache frequently accessed data in solid state
* Great for laptops as it extends battery life since platters don't spin as much.
* Apple also uses what they call *fusion drives*. Same thing.

## Connecting Mass Storage

* 