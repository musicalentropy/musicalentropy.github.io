---
layout: post
title: JUCE 5.1 DSP module
---
In July 2017, I did work again for [ROLI](https://roli.com/) and the [JUCE](http://www.juce.com) team, to improve the SDK I use all the time to develop multi-platform audio applications and plug-ins, and to provide some DSP code that has been included since in the so-called [DSP module](https://juce.com/releases/juce-5-1).

{% include youtubePlayer.html id="ZrxrhGg7_xA" %}

I even spent one week in [FXpansion](https://fxpansion.com/) headquarters to work in a hellish but fun pace ! And I had a great time hanging out with the JUCE + FXpansion guys. Basically, I provided some code to help JUCE users writing plug-ins who need a convolution engine, filter design and processing functions, oversampling, some fast approximation of functions...

I have written this blog message today because recently I have create a few topics on the JUCE forum related with my work, and I wanted to post links to them there :

* [DSP module discussion / Structure of audio plug-ins API](https://forum.juce.com/t/dsp-module-discussion-structure-of-audio-plug-ins-api/23589)
* [DSP module discussion / New Oversampling class](https://forum.juce.com/t/dsp-module-discussion-new-oversampling-class/24153)
* [DSP module discussion / New AudioBlock class](https://forum.juce.com/t/dsp-module-discussion-new-audioblock-class/24154)
* [DSP module discussion / IIR::Filter and StateVariableFilter](https://forum.juce.com/t/dsp-module-discussion-iir-filter-and-statevariablefilter/23891)
* [DSP module discussion / Fast function computation classes](https://forum.juce.com/t/dsp-module-discussion-fast-function-computation-classes/24905)
* [DSP module discussion / New class SIMDRegister](https://forum.juce.com/t/dsp-module-discussion-new-class-simdregister/24911)
* [DSP module discussion / New classes in the maths folder](https://forum.juce.com/t/dsp-module-discussion-new-classes-in-the-maths-folder/24908)

Otherwise, I'll be again at [ADC 17](https://www.juce.com/adc-2017) this year in London, presenting a talk called [Fifty Shades of Distortion](https://www.juce.com/adc-2017/talks#fifty-shades-of-distortion) (which will be on Youtube a few weeks later), and I'll update Spaceship Delay when I'm back with a few improvements + new functionalities !

