---
layout: post
title: Crimping coax connectors
published: true
---

I used to really hate wiring up coax connectors. I'd decide I needed to wire up a lead for some purpose and order the plugs.
They'd arrive and then get put in a box somewhere never to see any cable. Soldering PL259 UHF plugs never seems to work.
Although the centre pin is easy 
to solder, if you don't file it down it then sticks in the socket and forcing it apart breaks something. Then trying to solder the braid 
seems impossible. If you manage to apply enough heat to the plug's body to get a decent joint, it melts the dielectric and you get a 
short between inner and braid.

Because of all this I decided to use phono (RCA) sockets on all my homebrew QRP gear. But these aren't great either. They actually work 
fine electrically for RF, especially at QRP levels, but the plugs have still given me grief. You have to file the plugs to take RG58 
cable 
and then the plastic shroud doesn't stay on the plug and it's impossible to remove it from a tight socket (such as my phono-to-BNC 
adapters). 
But because I hated fitting UHF and BNC connectors they were the best option.

### Crimping

But I finally decided I wasn't happy with the phono plugs and invested in a crimp tool.

I chose this [crimp tool](https://cpc.farnell.com/duratool/d03016/f-bnc-tnc-n-crimp-tool/dp/TL02031) from CPC:
![Crimp tool](https://cpc.farnell.com/productimages/standard/en_GB/TL0203106-40.jpg) specifically because it claimed to do
RG174 cable as well as RG58. I wanted to be able to wire connectors with the thinner cable as I like to experiment with portable and
SOTA antennas.

I've found the best tutorial for how to crimp connectors is this Youtube video:

{% include youtubePlayer.html id=ktQVwfo-s9w %}

CPC and all the other suppliers seem to stock a huge variety of connectors which seem to be very similar. I ordered some crimp BNC 
connectors for RG58 and RG174 cable. I made a BNC to BNC lead with RG58 really quickly - I just had to fiddle with the wire stripping 
but it went together easily. Compared to soldering it actually made fitting connectors a joy.

### RG174

Unfortunately RG174 wasn't as easy. Despite the crimp tool claiming to support RG174 it didn't have the right size die for the crimp 
sleeve and
it jammed. A few minutes desperate Googling found how to release the tool. The connector was crimped but it didn't look as neat as it should. Although it seemed to work I didn't trust it. And having to release a jammed crimper every time was not ideal!

An email to CPC's technical support eventually got a reply saying it should work. In the meantime I'd done my own research and had found a datasheet for BNC plugs that are available for RG58 and RG174 cable that use exactly the same dies - and they were on my crimp tool. I actually found the datasheet on the RS website but bought the connectors from CPC. And they worked on the RG174 cable.

The connectors are from TE Connectivity. The links are to CPC:
|Coax type|Connector|
|---------|---------|
|RG58|[5-1634500-2](https://cpc.farnell.com/te-connectivity/5-1634500-2/plug-str-bnc-crimp-50r-rg58c-u/dp/CN10202)|
|RG174|[5-1634500-1](https://cpc.farnell.com/te-connectivity/5-1634500-1/plug-str-bnc-crimp-50r-rg174a/dp/CN10204)|
[Drawing and wiring info from RS.](https://pdl.designspark.com/api/v1/manufacturers/53f31a629b4759f8698ba80b/part/53f3285e9b4759f869acd252/55bfad6b8759c5ef5e8bf9f4/1.pdf)
