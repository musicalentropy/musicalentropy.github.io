---
layout: post
title: Spaceship Delay Anecdotes
---

I'd like to share something cool with you today !

When I was working on the modeling of the Echocord Super 76, I spent a lot of time doing measurement, and I have only tried to do something from them a few days before the KVR Developer Challenge deadline, to include the spring reverb impulse response in my plug-in. However, after the first calculations, here is what I got :

{% include soundcloudPlayer.html id="https://api.soundcloud.com/playlists/281820680" %}

I was scared because I thought that I did something wrong with the measurement itself, like having a feedback loop in the recording that I didn't saw at first, and I thought all my recordings were screwed up. You can imagine what was the impact of this a few days before deadline, with no way to redo easily the recordings since I don't own the device. Fortunately, it turns out that there was a bug in my deconvolution algorithm, and so everything was finally fine !

However, I tried to re use the "wrong" impulse response again a few days ago, and I thought that the sound I got is somehow really cool, so I thought it might be a good idea to share it with you ! I have added some artificial decay on the reverb tail so it doesn't stop too suddenly. You can find it here :

[Impulse Response](http://musicalentropy.github.io/files/ErrorImpulseResponse.wav)

It happens a lot of times during development to have some kind of "interesting accidents", when a bug or an unexpected thing happens in the code, and gives interesting sonic results...

Enjoy !