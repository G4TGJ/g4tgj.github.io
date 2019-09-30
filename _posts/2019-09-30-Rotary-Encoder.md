---
layout: post
title:  Rotary Encoder
published: true
---

My 40m homebrew transceiver is controlled by an Arduino Nano clone. The tuning knob is a rotary encoder which has three pins - 
ground, A and B. A and B are connected to digital inputs with an internal pull-up resistor, so when the pin goes active a 
logical zero is read. Rotating the control produces two square waves in quadrature. For example, a series of counter-clockwise
clicks produces the following:

![Quadrature Diagram](/images/Quadrature_Diagram.svg)

This diagram is from [Wikipedia](https://en.wikipedia.org/wiki/Rotary_encoder).

Reading the state of A and B on each transition gives the following for clockwise and counter-clockwise:


|CW||||||
|-|-|-|-|-|-|
|A|0|1|1|0|0|
|B|0|0|1|1|0|


|CCW||||||
|-|-|-|-|-|-|
|A|0|0|1|1|0|
|B|0|1|1|0|0|


My first code to handle this was simple. I noticed that A is 1 for two transitions and on the second the state of B indicates 
whether movemement is CW or CCW. This led to the following code snippet:

```c
if( (bRotaryA != prevbRotaryA) || (bRotaryB != prevbRotaryB) )
{
    if( prevbRotaryA && bRotaryA )
    {
        if( !prevbRotaryB && bRotaryB )
        {
            *pbCW = true;
        }
        else if( prevbRotaryB && !bRotaryB )
        {
            *pbCCW = true;
        }
    }
    prevbRotaryA = bRotaryA;
    prevbRotaryB = bRotaryB;
}

```

This worked well but I began to notice some strange effects. When rotating the control quickly clockwise to increase the
VFO frequency, it would occasionally go backwards, to a lower frequency. Making seemingly unconnected changes to my code, 
or changing compiler optimisation level, affected the prevalence of the problem. It was obviously a timing problem.
Clearly my logic needed to be cleverer and do
some debouncing.

The solution was to count both A and B pulses and only register movement when there were two pulses on each:

```c
// Only do something with the rotary control if there is a change
if( (bRotaryA != prevbRotaryA) ||
    (bRotaryB != prevbRotaryB) )
{
    // We need to debounce the control
    // The two outputs run in a set sequence so we ensure this is
    // followed.
    // Count the A and B pulses
    if( bRotaryA )
    {
        countRotaryA++;
    }
    if( bRotaryB )
    {
        countRotaryB++;
    }

    // If we have had 2 pulses from A and B then we are happy
    // we have properly rotated
    if( (countRotaryA == 2) && (countRotaryB == 2) )
    {
        // Whichever line is high tells us whether we are going CW or CCW
        if( bRotaryA )
        {
            *pbCCW = true;
        }
        else if( bRotaryB )
        {
            *pbCW = true;
        }
    }
    // If the control is back to its idle position then reset the counts
    if( !bRotaryA && !bRotaryB )
    {
        // Reset the counts
        countRotaryA = countRotaryB = 0;
    }

    prevbRotaryA = bRotaryA;
    prevbRotaryB = bRotaryB;
}
```
Now the control works perfectly.
