---
layout: post
title:  Morse Keyer
published: false
---

During these difficult coronavirus times I seem to be as busy as ever. I am lucky enough to still have a job that I can do from home, 
plus I have two daughters who need help with their home schooling. And the good weather means we are spending lots of time in the garden -
it might actually look tidy soon. However, I have decided to do some lockdown projects and here is my first, a morse keyer.

![Morse Keyer Photo](/images/MorseKeyerPhoto.png)

It is a very simple circuit as it uses an ATTiny85-20PU microcontroller which actually packs in a lot in its 8 pin package costing about 
a pound. Most of the work is in the software but I had already written a keyer for my transceiver project (which I will publish here
one day, but it is continually changing as I tinker).

![Morse Keyer Circuit](/images/MorseKeyer.png)

U1 is the ATTiny and it is powered by BT1, a 3V coin cell. I'm using a CR2025 as I have loads of these spare (they come in a pack with 
CR2032 which are used by a number of household items) but the holder will take any cell with the same diameter. The hardware and software
are designed to use as little power as possible (more on this later).

C1 and C2 are decoupling and reservoir capacitors. Although the power consumption is very low U1, like all digital circuits, will draw its
current in bursts and these capacitors ensure the supply voltage doesn't dip. This will become particularly important as the battery 
discharges and its internal resistance rises. C1 should be placed close to U1.

J1 is the header for ISP (In-system programming). This is needed to program the ATTiny. If you have the means to program the chip
externally you could omit this, but it makes life a lot easier while developing the software. See later for more on programming.


