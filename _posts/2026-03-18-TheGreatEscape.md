---
layout: post
title: The Great Escape Final Release
---

Hello everyone! Today, I'm going to talk to you about the latest version of **my freeware The Great Escape**, and also a little bit about the development history of this plug-in, something I didn't have the opportunity to do here when it was released. You can still find it here:

[The Great Escape by Musical Entropy](https://musicalentropy.com/TheGreatEscape.html)

The plug-in was therefore created at the end of March 2020, during the infamous COVID lockdown. I had seen a few initiatives from artists and developers who wanted to communicate the importance of respecting the lockdown and who were offering ways to keep people busy and make it more fun, and I thought the idea sounded very interesting. So I decided to do something along those lines and developed everything in just a few days, without any vibe coding :)

Moreover, a few weeks earlier, I had the chance to participate in a show in Paris, called Festival United Guitars 2020, organized by Ludovic Egraz, editor-in-chief of [Guitare Xtreme magazine](https://guitarextrememag.com/), and leader of the musical project of the same name [United Guitars](https://united-guitars.fr/) which showcases compositions produced by some of the best French guitarists.

![United Guitars Volume 4]({{site.baseurl}}/images/artwork-UG4-retouch-1015x1024.jpg)

At that show, I had the chance to try out a few pedals, and I was particularly fond of the famous The Great Escape by Thrilltone. This tremolo sounded really good, and using dynamics to manipulate its parameters with just a few knobs struck me as a brilliant idea, and a fun way to rediscover playing with a tremolo. Just a few days later, I loved the concept so much that I tried to recreate it in a plug-in, mostly by ear, especially the dynamics side. And that resulted in this magnificent prototype :)

![Prototype du plug-in The Great Escape]({{site.baseurl}}/images/TheGreatEscapePrototype.png)

When I decided to release a new freeware, the idea of completing this modeling work seemed very good to me, especially since I had the opportunity to discuss with [Pierre-Benoît Prud'homme](http://thrilltone.fr/), the founder of the pedal and the Thrilltone brand, which also makes great distortion pedals + others, whose graphic aesthetic I greatly appreciate (just look at this beauty):

![Thrilltone Northern Lights]({{site.baseurl}}/images/Northern-Lights-009-600x600.png)

So we got in touch, and the idea of releasing a paid software tremolo emulation, initially with a rough model in a free version, seemed like a good one. The freeware plug-in was released as a VST/VST3/AU/AAX and even a Linux version, a first for me at the time. The plug-in regularly displayed lockdown recommendations, which I removed in a later version, and used the original pedal graphical designs, generously provided by Pierre-Benoît.

The idea was to discuss collaboration again for the paid version later, and to properly promote the original pedal as well, which apparently sold a bit better thanks to me! We'll also skip over the fact that the freeware included an Easter Egg that's still there and is quite entertaining in itself :)

I'll mention again that this is an analog tremolo emulation, with **its subtle touch of signal coloration** even when the tremolo isn't active. Beyond its sounds, it distinguishes itself from a classic tremolo by its ability to easily **add variety to the effect** itself, using a parametric envelope follower that can vary the speed and amount of the tremolo based on the signal's dynamics.

![The Great Escape 1.2.0]({{site.baseurl}}/images/the_great_escape_manual.png)

The whole thing is also very well explained in the original manual, in the educational aspect of my plug-in which I had particularly pushed, and applies equally well to guitars as to vocals or synthesizers sounds.

![The Great Escape 1.2.0]({{site.baseurl}}/images/the_great_escape_tutorial.png)

Then, very recently, and as you know, I released a new version of the plug-in.

![The Great Escape 1.2.0]({{site.baseurl}}/images/TheGreatEscape-1.2.0.png)

This project allowed me to incorporate the latest updates to the JUCE framework and my codebase, properly implement support for the latest operating systems, add CLAP to the list of available formats (currently only on Linux), and to refine the emulation to better match the behavior of the original pedal, which I now own. However, paid collaboration is unlikely, and for this reason I've focused on creating an emulation that closely resembles, but isn't strictly identical to the original, with a few improvements over the initial version I released. 

{% include soundcloudPlayer.html id="https://soundcloud.com/musicalentropy/little-wing-65-tge?in=musicalentropy/sets/the-great-escape-audio-demos" %}

In any case, I'm very proud of this plug-in, very happy to have been able to work with Pierre-Benoît on the emulation of his awesome software tremolo, and I'll keep you updated on my upcoming releases and work. I'll have some announcements to make very soon about that :)

Stay safe and stay tuned!