---
layout: post
title:  Tiny AVR 1-Series
published: false
---

I've been using AVR microcontrollers for a few of my projects. The ATtiny85 is a great little 8-pin DIP or SOIC chip which is perfect for a morse keyer or controlling an LCD
display over I2C. For those projects requiring more program space I've used the ATmega328P in the form of an Arduino Nano, but this is quite large and the only surface mount
part is in a package I'm not confident I can make a PCB for or solder. The ATtinies are limited to 8K program space which is just not enough.

In 2016 Atmel launched the tinyAVR 1-series. I thought the ATtiny3216 would be perfect for my projects. It has 32K flash and is available in a 20-pin SOIC package which is perfect.
One major change is the use of UPDI for programming the devices instead of the SPI based 6 pin header that the older parts use. UPDI only requires two pins which will simplify
things somewhat. But I can't use my USBasp programmer.

Atmel make a number of evaluation boards for their microcontrollers. There isn't one for the ATtiny3216 but I chose the ATtiny817 Xplained Mini as a close equivalent. The device
on these only has 8K of flash but the peripherals are all the same. But the

![16x2 LCD display](/images/lcd1602.jpg)
