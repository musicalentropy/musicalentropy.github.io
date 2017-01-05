---
layout: post
title: Machine Learning Hackathon
---
As you might not know yet, my main occupation today is being a freelance developer and audio signal processing engineer. I do consulting jobs mainly for companies in the audio industry. Last month, [ROLI](https://roli.com/) and the [JUCE](http://www.juce.com) team asked me to work on a Machine Learning JUCE module, in order to make it available for a special event, a Hackathon in London. JUCE is the famous SDK that is being used by more and more developers (including me) to release multi-platform audio applications and plug-ins.

![Machine Learning Hackathon](https://scontent-cdg2-1.xx.fbcdn.net/v/t31.0-8/15194335_1372787506067788_7919598285914712537_o.jpg?oh=905efe0d82e2f71921f422a1098a4b0f&oe=59193DE7 "Machine Learning Hackathon")

They started a partnership with the [Goldsmith University](http://www.gold.ac.uk/) in London and the [IRCAM](http://www.ircam.fr) in Paris, about their european project called [RapidMix](http://rapidmix.goldsmithsdigital.com/) for Realtime Adaptive Prototyping for Industrial Design of Multimodal Interactive eXpressive Technology (yes I know it's long). To summarize, it's a Machine Learning C++ toolkit/API, made for giving a fast and easy access to Machine Learning algorithms to developers and artists, in order to create innovative human-computer interfaces, for gesture recognition and creation of new musical instruments. 

So, two weeks before the hackathon, the JUCE team asked me to develop a JUCE module wrapping a section of RapidMix called RapidLib, created by [Michael Zbyszyński](http://www.mikezed.com/). It is the little brother of the [Wekinator](http://www.wekinator.org/), designed by [Rebecca Fiebrink](https://www.doc.gold.ac.uk/~mas01rf/Rebecca_Fiebrink_Goldsmiths/welcome.html) also at Goldsmith. You might know them for the amazing talks they did at the [Audio Developer Conference 2016](https://www.youtube.com/watch?v=8IEVWj_OYhM) in November, and for the MOOC [Machine Learning for Musicians and Artists](https://www.kadenze.com/courses/machine-learning-for-musicians-and-artists/info). I did code the module, some JUCE examples, and I did also a talk at the beginning of the Hackathon so everybody could grab the basic concepts and start doing something cool.

{% include youtubePlayer.html id="8IEVWj_OYhM" %}

You can see the slides I have used during my talk here : [Hackathon Slides]({{site.baseurl}}/files/HackathonSlides.pdf).

## Machine Learning ?

What's interesting here is that I didn't know anything at all or nearly about Machine Learning before ! But I learnt everything I could about the subject in that short amount of time in order to do the job successfully, and to be able to explain how to use the JUCE module and do cool things with it. Ultimately, everything worked as expected, and I also got nice reviews about my work and my talk from the people involved in the RapidMix project, for which I am very proud !

![Machine Learning](http://blog.euratechnologies.com/content/uploads/2015/04/machine-learning.jpg "Machine Learning")

Anyway, the reason I'm talking about that is to tell you how much I am excited about this collaboration and the things that are going to happen next. The JUCE module isn't available to public yet, since it is in a very early alpha version right now, but it will be released in the future, and the people who have been able to have fun with it already in the Hackathon were very happy to catch this opportunity too.

Then, why am I so excited about this ? Since I'm new in this area, I wouldn't be able to explain in details what is Machine Learning and how it works, but here is what I have learnt already (you can have a look for my talk slides too) :

* The very principle of Machine Learning is the use of an algorithm, which is **trained** with some data provided by the user. The **training set** of data is made of samples with inputs + associated outputs. This algorithm then is expected to have a given behaviour, when receiving some **random** input data.

* There are two main kinds of Machine Learning algorithms, ones to do **classification**, and ones to do **regression**.

* In **classification** applications, the output of the algorithm is an integer variable or a class label. For example, a classification algorithm is trained with pictures of animals, and the associated animal names. When a new picture is given to it, the algorithm is supposed to be able to tell you what animal is in the picture.

* In **regression** applications however, the outputs are continuous, they can be any float/double variables. As an example of regression, imagine you want to model a mathematical function with a Machine Learning algorithm, like an hyperbolic tangent. You train your regression algorithm with a set of input + output data that you calculate yourself. Then the algorithm processes any input value and returns an output which is supposed to be as close as possible of the original mathematical function result.

* In order to train properly Machine Learning algorithms, it is common to use **features**, which means sampling a large amount of data and compressing it or extracting some meaningful information from it. For example in audio, it is possible to train an algorithm with a RMS value taken from a 200 ms buffer of audio samples, instead of feeding the algorithm directly with that buffer. It is also possible to extract some information such as the pitch, the frequency response etc. With a video signal, you can reduce the resolution of the image or extract a general brightness value.

## Applications of Machine Learning

Then, what can we do from all of this stuff ? In the audio examples I saw, regression algorithms were used to map and interpolate parameters of an audio synthesizer using controllers such as the computer mouse, a [Leap Motion](https://www.leapmotion.com/), some [ROLI Blocks](https://roli.com/products/blocks), a joystick etc. In her videos, Rebecca Fiebrink uses a lot of weird controllers and the Wekinator to create new instruments with new ways of interacting with a computer and making music. It is fun also to see that the musician can be involved during the training phase, and it is not all the time the duty of the application developer to train the Machine Learning algorithm.

{% include youtubePlayer.html id="rnlCGw-0R8g" %}

During the Hackathon, I coded something cool too (but I wasn't able to complete it before the end of the event unfortunately). I developed a drum machine application which can play 3 samples (a kick, a snare and a hi-hat sample), with 3 patterns that can be modified by the user with its mouse, or live if he connects a ROLI Blocks to its computer in USB. Then, he can "train" a classification algorithm with the microphone input of its computer, in order to associate outside sounds to one of the three patterns, using audio features extraction. This way, he can play the pattern 1 using a low-pitched sound for example, the pattern 2 with a white noise like impulse, the pattern 3 with anything else, whatever the user chooses. And finally, there is a simple delay audio effect with 4 parameters (delay time, feedback, mix, lowpass filter frequency) which can be "trained" with the mouse cursor. That means the user can associate the mouse cursor position with a given set of the 4 parameters, and then play with the audio effect simply by dragging the mouse over the window, which will move continuously its parameters like in the Michael Zbyszyński's talk. Sounds fun isn't it ? I promise, I'll make it available in a way or another at some point when completed.

The other participants did cool things too, even if it was difficult in a short amount of time to discover a new tool, a new technology, and to do something with them... But the beauty of JUCE is that it is possible to create a new project, handle all the dependencies of everything, and start coding in a few seconds ! The JUCE module during the hackathon featured simple classification and regression classes, but unfortunately nothing yet on the feature extraction side, which was the main concern of the participants at the time. We all had to code some on our own, which explains partly why I wasn't able to finish my application...

## Conclusion

Anyway, there is a JUCE module RapidMix being developed right now. Machine Learning is a hot topic nowadays thanks to all the communication about Deep Learning, or about some current applications related with audio such as speech recognition or automatic composition of music. I'm still discovering the topic right now, but in my opinion having something as simple as a JUCE module to let audio developers have fun with Machine Learning, thanks to the work of the RapidMix team, could be something huge for musicians and sound engineers. Not because Machine Learning would help creating really innovative stuff, I mean all the applications that I have talked about could be done without it. But because a lot of complicated problems can become very simple to solve thanks to Machine Learning, and because these algorithms allow to experiment a lot of things very quickly ! Finally, I think that current users of Machine Learning APIs / algorithms right now are most of the time in the academic world, and having something like a module in the JUCE library could make these features available easily to new people, with new application ideas, which is awesome.

I'd like to say also that I'm curious about the next developments in RapidMix, to see how it will perform compared with other Machine Learning APIs for C++. And I would love to add in Spaceship Delay some Machine Learning features I have in mind...

Anyway, thanks to all the people involved in this hackathon for organizing it, it was great to talk with them and with the participants back then !

## Bibliography

If you want to learn more about Machine Learning, there are tons of information sources on the internet, but I suggest you to have a look there in priority :

* [Machine Learning Crash Course Part 1, by Daniel Geng and Shannon Shih](https://ml.berkeley.edu/blog/2016/11/06/tutorial-1/)
* [Machine Learning for Musicians and Artists](https://www.kadenze.com/courses/machine-learning-for-musicians-and-artists/info)
* [The classic Andrew Ng's Machine Learning course on Coursera](https://www.coursera.org/learn/machine-learning/home/welcome)
