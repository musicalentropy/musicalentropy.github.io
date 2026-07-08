---
layout: post
title: Phaser Vibe for Logue SDK release
---

Hello everyone! 

Today, I'm going to talk to you about the release of a new freeware plug-in that has been made for the Korg Logue platform. Various products from the Japanese company indeed allow for the loading of third-party plug-ins, namely:

- NTS-1 and NTS-1 mk2
- NTS-3
- Minilogue XD
- Prologue
- Drumlogue
- microKORG 2

Depending on the plug-in, this allows the units to gain capabilities in areas such as delay, reverb, modulation, and general effects-as well as synthesis and sound generation-thereby making the devices in question far more versatile very quickly.

For my first foray into this platform - which I’ve particularly loved ever since I had the chance to review the [Korg NTS-1 for AudioFanzine](https://fr.audiofanzine.com/rack-numerique/korg/nu-tekt-nts-digital/editorial/tests/test-de-korg-nts-1-digital.html), an experience that allowed me to dive into the world of [associated third-party plug-ins](https://korginc.github.io/logue-sdk/unit-index/) - I chose to develop and release a somewhat unique type of effect: a phaser algorithm, called [Phaser-Vibe](https://www.musicalentropy.com/Logue-PhaserVibe.html).

I want to say that I particularly appreciate the effects and content Korg has offered in this regard. I’ve always had a soft spot for the reverbs found on each machine - such as "Submarine" or "Horror." However, I wasn't fully satisfied with the modulation options, especially the phasers - particularly given that I’ve had the opportunity to work on this subject over the years, notably while developing the Spaceship Delay plug-in. 

There are actually various ways to design a digital phaser algorithm, and each type produces a very different sound. Fundamentally, a phaser is an effect that mixes a "dry" signal with a "wet" signal processed by several all-pass filters in series. These filters do not affect the signal's amplitude-frequency response but do drastically alter its phase. This is how phasers operate in the analog world, and - most of the time - in the digital realm as well. 

While this phase distortion is barely audible on its own, it becomes noticeable when the single parameter of these first-order all-pass filters-the cutoff frequency around which the phase distortion is centered - is modulated (for instance, by an LFO). Depending on the LFO's waveform and the amplitude of the resulting pitch-shifting or vibrato effect (features sometimes found in commercial phasers), this creates a relatively subtle sound. However, the effect's characteristic sound emerges primarily when this processed signal is summed with the dry signal: the phase distortions transform into clearly audible notches-especially when they are in motion.

![Basic Phaser DSP signal path]({{site.baseurl}}/images/BasicPhaser.png)

It is also worth noting that these notches can be produced in various ways. Some digital phasers generate them directly-without relying on a mix between dry and wet signals-and allow for more advanced control over their spacing compared to the classic phaser design, which applies the same cutoff frequency to all all-pass filters, resulting in a somewhat predictable sound. Other phasers employ second-order all-pass filters, which further alters the characteristics of the effect. Then there are effects that create these notches using a short delay line, where the specific delay time determines the number of notches. This is the standard operating principle for chorus and flanger effects; in these cases, the notches are generally spaced linearly (with a constant frequency interval in Hz between them), whereas in phasers, they are spaced logarithmically (with a constant interval in octaves between them).

If we also add a feedback loop between the output and the input, these dips take on a different shape, and the effect becomes more pronounced-even taking on a somewhat metallic timbre.

![Effectrode Tube-Vibe]({{site.baseurl}}/images/EffectrodeTubeVibe.jpg)

So, what actually makes my phaser different from others? For starters, it features a very classic structure with a feedback loop, but the cutoff frequencies differ across the all-pass filters. This is actually quite unusual for analog phasers-except for Uni-Vibe clones or units influenced by them. Historically, those were the first types of phasers-originally designed to emulate Leslie cabinets in pedal form-and that specific characteristic (which gave my effect its name, unrelated to "vibe-coding") contributes to the sound of that legendary pedal (along with other factors, of course).

{% include soundcloudPlayer.html id="https://soundcloud.com/musicalentropy/sets/voyage-voyage-audio-demos" %}

Another point of interest is the shape of the modulation signal from the LFO and how it translates into an actual cutoff frequency for the all-pass filters. This might seem insignificant at first, but factors such as:
- the transition from a linear to an exponential curve,
- the inertia of certain components - like the optocouplers acting on the filters - which itself depends on the modulation depth or polarity,
- the initial waveform shape,

all contribute to the phaser's final audible signature; indeed, some analog phasers (and their emulations) derive their distinctive coloration from these characteristics, rather than simply from the number of notches.

![MXR Phase 90]({{site.baseurl}}/images/MXRPhase90.jpg)

Finally, let's add the modeling of all the signal filtering elements within the phaser beyond just the all-pass filters, such as the feedback path and the tendency of certain units (like the MXR Phase 90) to saturate in a specific way. Combine this with the algorithm's ability to accurately model feedback-specifically using the renowned "zero-delay feedback" techniques I’ve employed here instead of a simple delay-and you get a range of distinct tonal characters, including the one I’m presenting here!

![Spaceship Delay screenshot]({{site.baseurl}}/images/spaceship_delay_darkmode.png)

Incidentally, if you want to use it on something other than a Korg machine, it happens to be available in [Spaceship Delay](https://www.musicalentropy.com/SpaceshipDelay.html) as well, and can be used standalone. 

![Ornate Criminal from After Later Audio]({{site.baseurl}}/images/OC41.jpg)

Fun fact: there is also a version of my phaser algorithm in the [Phazerville Suite firmware](https://firmware.phazerville.com/) for my favorite Eurorack module, the Ornament & Crimes - specifically the Teensy 4.1 version like the After Later Audio Ornate Criminal, which features more I/O, new audio effects, more power, and more of everything. If you’re into modular synths, be sure to check it out too!
