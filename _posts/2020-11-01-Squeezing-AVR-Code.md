---
layout: post
title:  Squeezing AVR Code
published: false
---

With many of the tinyAVR family only having 8K of flash space it is sometimes necessary to squeeze your code really tightly to make it fit. Here are some tips on how to do this.

* Tell the compiler to optimise for space with -Os. If you are using Atmel Studio set it to build for Release.
* Avoid using printf (including sprintf).
* Avoid floating point. You can usually rearrange your equation to use 32 bit integer arithmetic. Note that some libraries can use floating point when you are not expecting it.
For example, I've seen baud rate calculations and microsecond delays use floating point.
* Avoid libraries (except for TARL of course!). Libraries are often written to be very general so they will work on any device in the AVR family so they have a lot of run time
overhead to cope with this. Also, many libraries use floating point when you don't expect it, which can be very expensive in terms of flash usage.
* Use C and not C++. I always use C as I assume that C++ will have an overhead although I have never tested this.
* Choose the right compiler version. Surprisingly, later versions of avr-gcc can produce larger programs.
* Use link-time optimisation. Adding the -lto option to the compiler can make a large difference when your program is spread over several source files.
* Other space saving compiler options: 
