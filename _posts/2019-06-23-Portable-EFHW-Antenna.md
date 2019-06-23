---
layout: post
title:  Portable EFHW Antenna
published: true
---

This is based on an article published in Sprat 177 (Winter 2018/19). There is also an update at the end.


As I want to be able to do HF SOTA activations I have been experimenting with portable antennas. My first effort was a 20m GP which is 
supported by a Sotabeams 10m travel mast ([instructions](https://www.sotabeams.co.uk/content/20m%20GP%20Instructions.pdf)) and I’ve
also made a 30m version. These give a low angle of radiation and I’ve not only tested them in my back garden but also on the beach while
on holiday in Scotland. However, it was a camping trip that made me realise that they are not always very practical. The radials and guy
ropes are very long and there was no way I could erect it by the tent. But there was a tree – if only I could just throw a wire up and
get on the air. So when I got home I experimented with an end fed half wave (EFHW).

The end of a half wave wire is very high impedance so it needs to be matched to the 50 ohms usually used for the transmitter.
As the voltage is high the current is low so, in theory, only a short counterpoise is needed. I’ve seen plenty of designs for EFHW
matching transformers but they always incorporate a capacitor in various combinations of fixed/variable and across the primary or
secondary. I’m never sure why the cap is needed so I thought I’d just keep it simple and see if it would work with just the transformer.
I had a spare FT140-43 ferrite toroid and wound 16 turns for the primary (antenna side) and 2 for the secondary (transmitter side).
I just used ordinary stranded wire and used a 3A connector block to make the connections. For the antenna I cut about 10m of wire for
the 20m band and just 1m for the counterpoise. I supported the wire on a 4m fishing pole and initially just pegged the end in the ground.
This gave an SWR of about 3:1. I then raised the end of the antenna and tied it to a convenient bush. This brought the SWR down to about
2:1. I then changed the primary of the transformer to 14 turns and found this brought the SWR down to 1.8:1. This made my FT817 very
happy and I managed a few contacts at 5W. I also managed a Bulgarian station with just 1W. So the concept was clearly sound.

It would be handy to have a choice of bands so I next added support for 30m. I added  about 4m of wire to the antenna and connected it
with crocodile clips. By tying the ends of wire with nylon cord you can easily change bands with the antenna erected. I also added about
2m of nylon cord to the end of the antenna so that it can be pegged into the ground without a high SWR. I didn’t have time for any
contacts on 30m but the SWR was similar to that on 20m and I was picked up by the RBN.

The next job was to make it a permanent solution. I rewound the transformer (14 turns primary and 2 turns secondary) with 20swg enamelled
wire and mounted it in a plastic box with two 4mm binding posts for the primary and a phono socket for the secondary. Note that there is
no earth connection between primary and secondary.

Further experimentation showed that although my SWR meter showed the same SWR on both bands the FT817’s own meter was not so happy on 
30m. I also noticed that removing the external meter caused the FT817 to see higher SWR. I experimented with longer counterpoises and
finally settled on 2m which now gives a consistent reading on both bands.

### Construction Instructions

For the antenna and counterpoise you will need:
* 16.1m wire
* 2.7m nylon cord
* 2 crocodile clips
* 2 banana plugs (optional but recommended)

For portable use I recommend bright orange wire and cord as it is very easy to trip over or lose plain stuff. These are available from
Sotabeams.

To make the antenna:
1. Cut 10.1m of wire. At one end attach a banana plug (if using). At the other end attach a crocodile clip, then fold back 20cm of
wire and tie a figure of eight knot. 
2. Cut 4m of wire. At one end attach a crocodile clip, then fold back 20cm of wire and tie a figure of eight knot. At the other end
fold back 10cm of wire and tie a figure of eight knot.
3. Cut 20cm of cord. Use this to tie together the loops at the crocodile clip ends of the wires. I used bowline knots for this.
![Crocodile clips and cord]({{ site.url }}/images/_D307431.jpg)
4. Cut 2.5m of cord. At one end fold back 10cm and tie a figure of eight knot to give a loop that can be used with a tent peg. 
Tie the other end to the remaining loop of wire made in step 2. Again, a bowline knot is best.
5. Cut 2m of wire and attach a banana plug (if using). This is the counterpoise.

To use, attach the antenna wire to one binding post of the transformer and try to get the other end of the wire as high as possible –
throwing in to a tree would be ideal. But it still works with the wire supported by a pole and the end pegged into the ground.
For 30m the crocodile clips should be clipped together and for 20m they should not be connected. The short counterpoise wire can be
positioned anywhere but if you find the SWR is too high you may need to adjust its position or even lengthen it.

In principle this should work on any band if the wire is a half wave but I haven’t tried it. The toroid needs to be ferrite and not
iron dust as it is a broadband circuit, but other sizes or mixes may work too.

### Update

 I have successfully used the antenna on a number of SOTA activations with contacts around Europe and to the States, all with 5W.
 I have also used the transformer with two more antennas. For 40m I used 20.2m of wire and for 80m I used 41m. These longer lengths
 are also usable on harmonics so the 40m EFHW works on 20m. The 80m also works on 40m and 20m. And you can add links for other bands too
 if you wish.

In September 2018 I used the 80m antenna supported in the middle by my 4m pole on an activation of Birks Fell (G/NP-031).
I managed 5 contacts on 80m (all but one
on CW) - I suspect it may not be so efficient at the lower frequency and suggest that more turns on a larger toroid would be worth 
trying. However, it was very successful on both 40m and 20m with 11 CW contacts on each. My FT817 shows a bar or two on its SWR meter
so it could probably be tweaked more, but since it doesn't fit in my garden I don't really fancy taking the wire cutters up the hill!
