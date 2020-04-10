---
layout: post
title:  Morse Keyer 2
published: true
---

I have updated the software to [v1.1](https://github.com/G4TGJ/MorseKeyer/releases) for the keyer so that the keyer mode and the slow and fast speeds can be set by programming the EEPROM with a
simple text file. This is easily done with avrdudess or other tool. This means there is now only a single hex file instead of different
versions for each keyer type. You can change these settings without having to rebuild the software - you don't even need to install
Atmel Studio if all you want to do is make the keyer and set your favourite mode and speed.
