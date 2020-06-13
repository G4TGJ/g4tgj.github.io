---
layout: post
title:  PCB Toner Transfer
published: false
---

There are lots of ways to prototype with through hole components - dead bug, Manhattan, Veroboard etc. But it is much harder 
with surface mount. I have used adapter boards with SMD ICs and have used a tile scribe to cut tracks on copper clad board but this is not
practical with ICs or for circuits of any size. So I have started making my own PCBs.

I've been using Kicad's Eeschema for some time for drawing schematics and so it didn't take me too long to get up to speed with PCBNew
which is the Kicad PCB software. Considering it is free I am very impressed. But the layout needs to be transferred to the copper clad
board and etched. The easiest way is to directly transfer laser printer toner to the board and use this as the etch resist.

I was initially inspired by this youtube video showing how nail varnish remover can be used to transfer the toner from a printout on
magazine paper. I tried this with various papers (Radcom, Radio Times, Which?) but all I
got was a big black smudge. My nail varnish remover (well my wife's) is 98% acetone and this dissolves the toner. The brand used in the
video has a long list of ingredients and it appears that alcohol is the other key ingredient. There are other videos showing that a 
ratio
of 3 parts acetone to 8 parts alcohol (ethyl or iso-propyl) is the best to use. I only add 70% IPA and I tried this but got no transfer
at all - presumably too much water.

The next thing to try was heat which is the more traditional way of doing toner transfer. I used an iron but others use modified 
laminators or heat presses. On a really small PCB this was moderately successful and I did manage to etch and build a small test
circuit, but when I tried with a larger design the transfer was poor. Trying to get even heat from the iron is hard - being a steam iron
means it has a lot of holes which presumably don't get hot. This is obviously why many use laminators or presses.

I ordered litre bottles of acetone and IPA from RS to have a go with the magic 3:8 formula. The first attempt was not good so I tried
with equal parts acetone and IPA. Again, I managed a small design but it was not good with a larger board. I a few different papers
but it didn't help.

Fortunately I had also ordered some Press n Peel Blue which is specifically designed for toner transfer onto copper clad boards. This
came just as I gave up on the chemical transfer. The instructions say to use on a temperature suitable for acrylic and polyester for
between 1.5 and 4 minutes. I set the iron to 2 and held it on the board, without moving, for 2 minutes and then spent the next 2 minutes
ironing all over the board in an attempt to get the toner to transfer properly this time. After a total of 4 minutes I ran the board
under the tap and peeled off the paper. To my delight the toner had transferred perfectly. In fact, it isn't just the toner that
transfers but the blue from the paper (which feels more like plastic) also. After etching in ferric chloride I had a perfect PCB.

Clearly some people are having great success with using ordinary paper to do toner transfer but there seem to be too many variables. If
you are lucky, or are prepared to spend a long timer experimenting, then I would suggest going straight for a 'proper' product such as
Press n Peel. At about £3 per letter size sheet (close to A4) it seems very expensive. But since I only need to cut a piece out which
is slightly larger than the PCB the 5 sheets I bought should last a long time.

I now have two large bottles of acetone and IPA which won't go to waste as they are perfect for cleaning duties (and I may even try
the chemical toner transfer again if I can find some cheap laser photo paper) I would recommend trying the proper product.
