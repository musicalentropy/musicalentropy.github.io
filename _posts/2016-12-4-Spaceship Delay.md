---
layout: post
title: Spaceship Delay presentation and KVR DC 16
---

Hello again !

Today, I'm going to present you the new freeware audio plug-in that I have released for the [KVR Developer Challenge 2016](http://www.kvraudio.com/kvr-developer-challenge/2016/). It is called Spaceship Delay, and you can grab it [here](https://www.kvraudio.com/kvr-developer-challenge/2016/#dc16-12755).

![Spaceship Delay Screenshot](http://static.kvraudio.com/i/b/screenshot-4.png)

I'd like to recall what the KVR Developer Challenge is. It's a contest for audio developers, where they have 2-3 months to develop something audio related of course (most of the time a plug-in, but also standalone applications, or sound librairies). Then, when the development period is ended, a voting period of 3-4 weeks start. All of the KVR audio website members, which is a very big audio/music forum, are invited to vote for their 5 preferred creations, and give them a rank. Then, at the end of the voting period, all the votes are counted, the ranks of all the contributions are established, and the creators can win a few things depending on the results.

I did that contest two times already. In 2012, I released [Inspiration](http://www.kvraudio.com/product/inspiration-by-musical-entropy/details), my take on the concept of Brian Eno's Oblique Strategies ported into a standalone application and insipred by some of my lectures from that time. Then, in 2014, I released [Guitar Gadgets](http://www.kvraudio.com/product/guitar-gadgets-by-musical-entropy/details), a VST/AU plug-in that time, which was a compilation of "fake analog pedals", a way to present a few audio effects algorithms put together in the same plug-in, and which could be very interesting for guitarists. My ranks at these times were 19th and 6th, which is honorable. I got also very nice reviews from a few places, such as a full page on Computer Music UK, and I learnt a lot of things in the process, both about coding/DSP and marketing. So, without thinking about it twice, I decided to do something again this year !

In fact, I came up with the idea of Spaceship Delay a long time ago already, I just decided to give it a go for the KVR DC 16 when I saw that KVR organized again a contest this year. The thing is I have all the Korg Monotron little synths at home, and even if I don't use that much, I love the idea behind, and more specifically I love this one :

{% include youtubePlayer.html id="CNXOI1AIjKo" %}

So I was thinking : what if you could use it as an effect ? And what about designing a convenient plug-in to do so ? A few hours later, I was coding a simple Korg MS-20 filter simulation, and I put it into a delay line. And it sounded already really amazing ! Then, 3-4 weeks ago, I started coding a plug-in using that simulation as a basis, and the all the important things that we would want in a good delay plug-in. I had also the chance to rent another amazing device, called the Dynacord Echocord Super 76, which is a tape delay machine with a spring reverb, more focused than a Roland Space Echo, but which sounds really good too. Now I don't have it anymore, but I have studied it for a few weeks, and I had captured some impulse responses from it. So, I decided also to include a simulation of that spring reverb thanks to convolution also, and I am very happy with the results.

![Dynacord Echocord Super 76]({{site.baseurl}}/images/Super76.png)