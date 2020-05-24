---
layout: post
title:  RF Changeover
published: false
---

I've been playing about with simple transmitters and receivers. The former are easy - a crystal oscillator, PA and key shaping circuit.
But receivers are much harder so I've been using my existing Arduino based direct conversion receiver. This means I need a way to
switch the antenna between RX and TX so I've built an RF sensing changeover circuit.

This circuit is from the book QRP Basics (2nd Edition) by the late, and much missed, Rev George Dobbs G3RJV.

![RF Changeover Circuit](/images/RFChangeover.png)

Normally the antenna is connected through the relay to the receiver. The transmitter is connected to a 50R resistor adequately rated for 
the transmitter power - it's effectively a dummy load but shouldn't actually be connected to the TX for long. The transmitter is connected
to the relay by a wire through a T37-43 toroid forming the primary of a transformer. The secondary is 5 turns of suitable wire - I used 
30SWG enamelled. This feeds to a diode detector to switch a MOSFET to energise the relay to connect the transmitter to the antenna. To
prevent the relay from chattering with the morse keying (or during speech pauses) C2 holds the MOSFET on for a period (determined by R2) 
to give semi-break in keying.

I used a 12V surface mount relay as that suits my standard 12V (or 13.8V) power supplies. In the original circuit the MOSFET was a 
VN10KLS which are now obsolete. I used a surface mount BSS123 but most small signal MOSFETs should work here, provided the gate 
threshold isn't too high.


![Morse Keyer Photo](/images/MorseKeyer.jpg)

