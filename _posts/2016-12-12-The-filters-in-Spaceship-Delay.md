---
layout: post
title: The filters in Spaceship Delay
---

In that new blog post I'm going to talk about the filter algorithms that are implemented in [Spaceship Delay](http://www.kvraudio.com/product/spaceship-delay-by-musical-entropy/details) ! Right now, you can see 4 different filter types in the filter section : Low/High Cut, Low/High Shelf, Japanese, and German/Canadian.

## Low/High Cut and Low/High Shelf

These filters are more or less the standard 2nd order filters or "biquads", modeling the analog circuit called State Variable Filter (SVF) behaviour, with a -12 dB/octave attenuation. The equations are derived from the famous [Robert-Bristow Johnson EQ Audio Cookbook](http://www.musicdsp.org/files/Audio-EQ-Cookbook.txt) that every DSP engineer in the world knows, and uses sometimes without even knowing. Same for most of filter algorithms available in commercial software. 

However, the original implementation does have some drawbacks well known, that I have been talking about in my recent [Audio Developer Conference talk](https://www.youtube.com/watch?v=esjHXGPyrhg). The two main drawbacks applies to the behaviour of the filters in the high frequency range, and when the cutoff frequency is modulated fast. In the first case, a lowpass filter for example is attenuating way too much the high frequencies close to half of the sampling rate. In the second case, a quick modulation with the original implementation, using a simulation structure called Direct Form, produces high amplitude artefacts at modulation. 

In Spaceship Delay, I have solved these issues by using another simulation structure called Topology-Preserving Transform, which is well documented on KVR forums (DSP section) and in the free e-book of Native Instruments Vadim Zavalishin, [The Art of V.A. Filter Design](https://www.native-instruments.com/fileadmin/ni_media/downloads/pdf/VAFilterDesign_1.1.1.pdf). I have also oversampled the filtering algorithm, since the section can produce some nonlinear stuff as we will see with the other kinds of filters. That gives me the right behaviour in high frequencies and when a parameter is changed by the user with automation. It will be even more useful if I decide to add in the modulation section in the future an envelope follower or a LFO modulating the cutoff frequencies. Moreover, this structure is already used in the phaser algorithm, for obvious reasons. 

I'd like to say there is absolutely nothing really innovative there, since this kind of filtering algorithm can already be found in most of current commercial plug-ins involving filtering. The Low/High Cut feature in Spaceship Delay has nothing groundbreaking either, and that's something that we find in most of other delay plug-ins, so its presence here is more than relevant without being something particularly new. However, I have not seen a lot of times some low and high shelf filters in this context, and I thought it would be a nice addition to drive further the nonlinear sections, put the delay line into resonant feedback in an interesting way, or simply to cut some frequency content like with the Low/High Cut filters in a different way. It's my friend François-Maxime from [Les Liens du Son](http://www.lesliensduson.com/) who suggested me this to do this and he was right !

## Japanese

The Japanese filter is obviously my take on the MS-20 / Monotron filters. You can find a very interesting study of its behaviour on Tim Stinchcombe's website, that I have been reading a lot during the development.

[Tim Stinchcombe study of Korg MS-20 filter](http://www.timstinchcombe.co.uk/index.php?pge=korg)

I'm not that proud of the realism and simulation quality of the result, since I'm still new in synthesizer filter modeling. But I think that the "japanse filter" in Spaceship Delay sounds quite good and is very interesting when put in a delay line, to get that screaming oscillating feedbacks everybody loves in "analog" delay software/hardware. As I said before, doing a delay and using that filter algorithm was the starting point of Spaceship Delay in terms of DSP. I wanted something that sounds a little like my Korg Monotron Delay, that I could use as a plug-in. I thought also that using other kinds of "Virtual Analog" filters in the delay line should be interesting too. So I did some research, trying also to dismiss the too obvious choices for adding a extra V.A. filter in the plug-in, and then I ended up doing modeling of the filter I called "German/Canadian".

## German/Canadian

For those who have read the embedded tutorial in Spaceship Delay, or seen the other blog posts, you already know the true identity of that filter. It is the one that can be found in the [Meeblip Anode and Triode synthesizers](https://meeblip.com/), made by Peter Kirn from [Create Digital Music](http://cdm.link/) and James Grahame from [Blipsonic / Meeblip](https://meeblip.com/).

{:refdef: style="textalign: center;"}
![Meeblip Anode and Triode]({{site.baseurl}}/images/Meeblip-synths.png){: refdef}

I spent a lot of time studying the schematic of the filter that is available on [GitHub](https://github.com/meeblip), covered by a permissive Creative Commons and GPLv3 license, since the Meeblip hardware + software is open source ! I wanted a filter in Spaceship Delay which would have second order attenuation like the Korg MS-20 filter (and not like the famous ladder filters), and the result sounded surprinsingly good too when put in a delay line.

My implementation, like for the Korg MS-20 filter, isn't that realistic yet, since I used a simplified model, and because I have not reproduced yet the same mapping for the cutoff and resonance knobs than the one in the original units. However, my model is based on the equations of the original circuit, that I have studied first in [LTSpice](http://www.linear.com/designtools/software/) and then in a simulation context to make it sound as good as possible.

![LTSpice Screenshot]({{site.baseurl}}/images/Meeblip-LTSpice.png){: refdef}

As you can see, for people knowing how to read a synthesizer filter schematic, it's a filter looking more or less like a Twin-T VCF, acting like a lowpass filter, but removing also a little in the bass frequency range, giving it a very interesting sound signature in my opinion. It is possible to study it further by determinating its transfer function from the electronic equations :

$$ H(s) = - \frac{R_2}{R_1} \frac{1 + C s (2 R_F + R_Q) + R_F R_Q (C s)^2}{1 + C s (2 R_F + R_Q) + R_F (R_2 + R_Q) (C s)^2} $$

I've made it zero delay feedback, but the way it saturates is still far from the original in my opinion, so I'm going to improve my model over the next weeks, and I'll probably start by updating the mapping of the controls so it behaves like the original at least in a strictly linear sense.

As a side note, don't forget to get the last version of Spaceship Delay to experiment with this filter, since the algorithm has changed a little since the beginning of the KVR Developer Challenge, to solve a few issues I had.

## Next steps for Spaceship Delay

I got already tons of very nice comments, and feature requests for Spaceship Delay. I even got a very nice new skin proposal from a user of the KVR forums. I'll probably spend a lot of time after the voting period to add the most interesting features people have submitted, and a few things I had also in mind and that I have not been able to finish before the deadline. But, what I can already tell you, is that I'm already working on the AAX version of the plug-in, and it should be available in a few days !