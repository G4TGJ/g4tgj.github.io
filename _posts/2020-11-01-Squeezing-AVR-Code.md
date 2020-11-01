---
layout: post
title:  Squeezing AVR Code
published: true
---

With many of the tinyAVR family only having 8K of flash space it is sometimes necessary to squeeze your code really tightly to make it fit. Here are some tips on how to do this.

* Tell the compiler to optimise for space with -Os. If you are using Atmel Studio set it to build for Release.
* Avoid using printf (including sprintf).
* Avoid floating point. You can usually rearrange your equation to use 32 bit integer arithmetic. Note that some libraries can use floating point when you are not expecting it.
For example, I've seen baud rate calculations and microsecond delays use floating point.
* Avoid libraries (except for [TARL](https://github.com/G4TGJ/TARL) of course!). Libraries are often written to be very general so they will work on any device in the AVR family 
so they have a lot of run time
overhead to cope with this. Also, many libraries use floating point when you don't expect it, which can be very expensive in terms of flash usage.
TARL is a source code library which is configured at compile time and it is lightweight so it may not be so easy to use as other libraries but should produce smaller code.
* Use C and not C++. I always use C as I assume that C++ will have an overhead although I have never tested this.
* Choose the right compiler version. Surprisingly, later versions of avr-gcc can produce larger programs.
* Use link-time optimisation. Adding the  -flto -fno-fat-lto-objects options to the compiler can make a large difference when your program is spread over several source files.
* Other space saving compiler options: -fno-inline-small-functions -fno-split-wide-types -fno-tree-scev-cprop
* Linker relaxation: Add -Wl,--relax to the linker options.

I tried the various options with a program for the ATtiny817 and got the following:

|Program memory usage||
| ---|---- |
|Original|5146|
|-Os|4920|
|Remove floating point|4410|
|Remove sprintf|2880|
|Link time optimisation|2368|
|Other optimisation flags|2368|
|Linker relaxation|2366|

This shows that it's possible to more than halve the space used with sprintf using a big chunk. In this case, the other compiler flags made no difference.

In another program for the ATtiny85 the code would not originally fit in the available 8192 bytes even with -Os and avoiding sprintf and floating point:

|Program memory usage||
| ---|---- |
|Original|8852|
|Link time optimisation|8138|
|Other optimisation flags|8120|
|Linker relaxation|8120|

In this case the other compiler flags made a small difference but linker relaxation made no difference. Since these flags appear to do no harm there is no reason not to use them
(unless execution speed is crucial which is a very different optimisation problem).
