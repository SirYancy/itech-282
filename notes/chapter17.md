---
layout: default
title: Chapter 17 - Display Technologies
nav_order: 8
permalink: /chapter-10
mathjax: true
---

Chapter 17 - Display Technologies
=================================

Ever see a monitor that was bright on one edge but fades to black at the other?

Monitor
: Also called video display. Shows you what's going on. primary output device for most computing devices.

Display Adapter
: Or *video card* handles all communication between CPU and display

* OS needs to know how to talk to display adapter and needs appropriate drivers and configuration

## Video Displays

* Almost all computers use LCD monitors.
* CRTs show up on 1002 exam in the section on toxic waste disposal.

## How LCDs work

* Light has polarity
* Light travels in waves
* wavelength determines color.
* Imagine shaking a jump rope randomly.
* Light at many wavelengths creates white light.
* If there's only one wavelength, you will see that color
* A polarized filter takes the 3 dimensionality out of the light, but lets all the colors through.
* Sunglasses are often polarized.
* Imagine taking two polarizing filters and hold them at 90 degrees.
* Now take a third polarizing filter and put it between the two and rotate it to 45 degrees.
* So liquid crystals take advantage of this weird twisting of light waves.
* Liquid crystals are a liquid full of long, thin crystals that always want to orient the same direction.
* It's basically a liquid polarizing filter.
* So let's take two sheets of glass and cut fine grooves in one side of one sheet.
* Pour the liquid on it and it'll settle into the grooves.
* Go through images in text. (p 739-742)
* If there is no charge, the crystals will twist and let light through
* If there is a charge, they will orient to the charge and block light.

## LCD displays

* Tiny liquid crystal molecules (sub-pixels)
* arranged in rows and columns between polarizing filters.
* A sheet above the sub-pixels is colored red, green, blue
* Each set of three is a pixel
* So how do you get a charge to each pixel?
* static (calculator) displays don't work. Too inflexible
* Early LCDs used matrix of wires.
    * vertical Y wires run to every sub-pixel in the column.
    * Horizontal X wires run to each row of sub-pixels.
    * There has to be a charge on both X wires and Y wires to light a single sub-pixel.
    * If you want color, you use three matrices.
    * They are intersected very close to each other. 
    * A sheet of glass is covered with tiny red, green, blue dots.
    * This is called *passive matrix* LCD
* Current LCD monitors use *thin film transistor (TFT)* or *active matrix* tech
    * One or more tiny transistors control each color dot. Faster display, crisp definition, better color control.
    * Check p 744
* LCD monitors have two or three main components
    * LCD Panel
    * backlights,
    * inverters (older models)

### LCD Panel Tech

* LCD manufacturers use a lot of variations.
* Most common today are 
    * *twisted nematic (TN)* (fastest)
    * *in-plane switching (IPS)* (best color)
    * *vertical alignment (VA)* (kind of in between)
* We'll come back to that

### Backlights

* These vary according to technology used.
* Current LCDs use LEDs
* Older generations used CCFLs
* LEDs took over because 
    * they use DC electricity
    * consume much less electricity
    * generate no heat
    * They're also super small
* Typical configuration is two LED lights. Top and bottom. *edge LED backlighting*
* Drawback is light bleed or edges a little brighter
* *Direct LED backlighting* puts a bank of LEDs behind the panel.
* This is more expensive and uses more electricity
* Early LCDs used *cold cathode flourescent Lamp*.
* So these use high freq AC. So you need an inverter
* These LCD screens were much thicker than today

### LCD Variations

* Let's hit variations.
    * Resolution
    * Brightness
    * Viewing Angle
    * Response Rate
    * Refresh Rate
    * Contrast Ratio
    * Color Depth.
* **Resolution**
    * Resolution is number of pixels on the display.
    * Number of pixels up x number down.
    * LCDs are designed to run at a single *native resolution*.
    * It cannot run at any higher res
    * And running at lower res degrades image quality
        * They use a technique called *interpolation* to soften edges of pixels.
    * Always set at native res.
    * These resolutions have names. *video modes*.
    * 640x480 *(VGA)* - The only one that's actually on the exam.
    * 1366x768 *(WXGA)*
    * 1920x1080 are called *FHD* or *1080p*.
    * *aspect ratio*.
        * 16:9 is a typical widescreen aspect ratio
        * Video might like 21:9
    * Consider what devices have what kinds of ratios
    * Consider the relationship between screen size and resolution (PPI)
* **Brightness**
    * Strength of backlights determines brightness
    * Measured in *nits*.
    * 100 nits on the low end. 1000 nits on the high end.
    * Average is around 300
    * One nit is one candela/m<sup>2</sup>.
* **Viewing Angle**
    * viewing angle is limited.
    * screen fades at extreme angles.
    * TN panels have narrow angle
    * IPS tech has a huge viewing angle.
    * Sometimes you *want* a limited viewing angle.
* **Response Rate**
    * The amount of time it takes for all sub-pixels to change from one state to another.
    * This is measured in ms
    * lower is better
    * Two ways to measure this:
        * BtW
        * GtG
    * Typical advertised response rate is 5ms
    * Though this is usually GtG.
* **Refresh Rate**
    * How often the screen changes or updates completely
    * Sort of like clock speed
    * 60 Hz is fine for most.
    * Note: Standard motion picture is 24 Hz.
    * Common higher end refresh speeds are 144, 165, 240
* **Contrast Ratio**
    * Some professions hung on to CRTs for a while. Why?
    * *contrast ratio* is difference between darkest and lightest spots the monitor can display.
    * good is 450:1
    * low end is 250:1. High is 1000:1
    * *dynamic contrast ratio* - marketing hogwash.
* **Color Depth**
    * The bit-depth of the panel.
    * Old TN monitors used 6-bit panel. So, each sub-pixel could do $ 2^6 = 64 $ different color combos.
    * Today, they use 8-bit or $ 2^8 = 256 $ colors per channel. This is marketed as 24-bit color.
    * photographers might use 10-bit panels.
* **Comparing**

## Display Adapters

* Display adapter or video card
* handles computing and processing information from CPU and sends it to display
* It is a processor. Thus it needs RAM.
* Also needs fast connection to CPU and system RAM
* It must also have a connection compatible with monitor
* Often an expansion card plugged into mobo
* Sometimes it's integrated into the mobo. Still called a video card
* Six things:
    * display modes
    * mobo slot
    * graphics processor circuitry
    * video memory
    * integrated GPU
    * connectors

### Historical/Conceptual

* Modes
    * In the old days. Video was exclusively text-based
    * The screen was divided into a grid
    * Limited to drawing one of 256 characters
    * These characters were stored in the BIOS
    * These video cards were simple and cheap.
    * There were a *few* effects.
    * Limited to 80 characters per row, 24 rows of chars.
    * These were the days that RAM was expensive.
    * You need 80 x 24 = 1920 characters = 15,360 bits or 1920 bytes to fill the screen
    * This evolved into *graphics video card* which could control every pixel.
    * Needed more RAM. 320 x 200 pixels = About 8000 bytes. (still monocrhome)
    * As resolutions increased, the amount of RAM needed increased
    * Color is the next step
    * So how many bits do you set aside for colors? How many colors do you want?
    * Four colors? 2 bits per pixel. 16 colors: 4 bits
    * No more text-only mode cards. only bits per pixel now.
    * 256 colors: 8 bits per pixel.
    * *color depth* is always a power of 2. Why?
    * As more colors are added: more RAM
    * See text page 822 (Update this)
    * Windows and Linux are only able to display a fixed number of resolutions and color depths
    * These are called Modes
    * Video Electronics Standards Association (VESA)
    * All derived from the original: VGA

#### VGA

* IBM introduced *video graphics array* VGA standard
* 16 colors at 640x480
* It used an analog signal instead of a digital one
* This allowed 64 distinct levels for 3 colors (RGB)
* $ 64^3 $ or 262,144 possible colors.
* Caveat: Only 16 or 256 colors can be displayed at a time.
* 640x480 and 16 colors is VGA mode.

#### Beyond

* Many modes, but you don't need to know them all

### Motherboard slot

* Four ways 
* PCI (older monitors older systems)
* AGP (still old, but not as old)
* PCIe (Current video cards)
* Integrated

#### PCI

* Limited to 132 MBps (32-bit transfers at 33 MHz)
* How much throughput do you need for even modest graphics?
* Also consider that systems often have more than one PCI device

#### AGP

* *Accelerated Graphics Port*
* Single, special port. Dedicated to video
* No current mobos have them anymore
* 66 MHz 32-bits

#### PCIe

* replaces PCI and AGP in the end.
* All video cards PCIx16 connector (all lanes)
* Remember that PCIe 3.0 is capable for 8 GTps *per lane*.
