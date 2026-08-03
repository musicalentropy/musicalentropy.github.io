---
layout: post
title: How I designed a unusual Shimmer Reverb in one month
description: "Information and thoughts related to Voyage Voyage product design process."
cover: /images/covers/voyage_voyage.png
tags: [kvrdc, product design, voyages]
---

Hello everyone! In this new blog post, we're going to talk about the release of my latest plug-in, Voyage Voyage, a freeware Shimmer reverb and drone/texture generator currently competing in the latest [KVR Developer Challenge 2026](https://www.kvraudio.com/kvr-developer-challenge/2026/), available for Windows, macOS, and Linux in VST3, AU, and CLAP formats. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/X3ZavdSpb00?si=dqmbGDctfGw2ieAg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

We're going to talk about **product design**, a subject I'm currently very passionate about, and one that some developers occasionally discuss, such as Tomislav Zlatic from Bedroom Producers Blog + Flame Sound regarding the release of his plug-in [Vatra](https://bedroomproducersblog.com/2026/07/31/making-vatra/). 

You are about to read about the process I used to select the plug-in's final controls, in which little to no AI is used (I am still considering what I want to do with these technologies and what would constitute "fair use", which will be the subject of another blog post), how I laid out the graphical interface, the elements I focused on for this new competition entry like accessibility and sweet spots, the reasons behind this unconventional concept (reverb + instrument), and my general workflow when creating a plug-in, for people who would like to work with me on their own projects (don't hesitate to contact me using the [social networks](https://www.instagram.com/musical.entropy/) if you do!)

## A circular approach to designing products

Product design is a topic that has been a real obsession of mine for some time now.

As a freelance developer, I've had a few opportunities to be involved in this stage of plug-in creation, though, for the most part, my clients already had a fairly clear vision of what they wanted and came to me to address a specific, identified need (such as emulating a particular electronic circuit, testing various algorithms for a specific type of effect, or troubleshooting an existing project). 

What particularly interested me about this was seeing the extent to which completely unrelated fields could intertwine at this stage, ranging from graphic design, ergonomics, and UX design to researching best practices in existing products, and synthesizing the essential aspects of DSP blocks versus what should or could be made user-editable. 

But it also involves elements like marketing, which can, or indeed must, be considered during the design phase rather than after the product is finished, specifically regarding market fit. This determines whether communicating about the product will be easy or difficult: what generates hype versus boredom; what is innovative and requires user education versus what is commonplace or immediately familiar; and what is currently trending versus what doesn't yet exist in any form.

From there, we would look at the needs of musicians and future users, ranging from the needs they articulate to those they aren't even aware of, whether these foster creativity or simply provide practical utility, and even consider what inspires or empowers the tool's developers themselves (since those who spend their days creating plug-ins are often musicians or artists in their own right). We would also take into account the biases and blind spots shared by all these groups, their frustrations, and the underlying motivations for embarking on a new plug-in development project.

What fascinates me about this is that product design is a sort of **circular process** - one that integrates all these elements and fosters communication between them - yet it can also be a factor that negatively stands out in products that fail to achieve the expected success. Across all disciplines, we frequently see examples of products where questions regarding the viability of the product or service were raised only at a late stage, or indeed never asked at all.

## Ever faster and for less time

It must be said that, in this year 2026, I personally observe that many things have changed in the world of plug-ins. To summarize, I would say that the advent of AI has caused a stir, but has also accelerated a number of things that already existed, such as market saturation or the continuous devaluation of plug-ins that are put online, driven in particular by the phenomenon of "promotional periods that are no longer the exception," with these famous plug-ins officially on sale at 250 euros but whose average value over 365 days is less than 25% of this price, with a minimum of 5-6 different promotional periods per year (see for example these *deals* from the [promotions page of the Synth Anatomy blog](https://synthanatomy.com/category/best-music-tech-plug-in-deals-you-need-to-know/plug-in-deals)).

![Deals from Synth Anatomy]({{site.baseurl}}/images/synthanatomy_deals.png)

Furthermore, some of my clients (those who rely on human expertise) have faced mounting pressure to alter their development practices to ensure their products succeed in these peculiar times. This involves issues such as the time spent developing a plug-in versus the need to accelerate production to churn out ever more plug-ins, even if the resulting software offers fewer features and receives support for a shorter period. This battle for the attention of potential users is waged not only against direct industry competitors but also against other leisure activities beyond music creation, and even against the passive consumption of educational content that is rarely put into practice.

But above all, for me, it highlighted flaws in their product design approach, flaws that weren't significant five years ago but cause concrete problems today. That is why I began educating myself on the subject and increasingly advising my clients on it over time, with a strong focus on monitoring industry best practices, particularly among a few key brands.

## Create a new freeware plug-in in 2026?

When the KVR DC 2026 was announced, I have to admit I wasn't keen on participating, given my work schedule at the time and the fact that I hadn't yet fully visualized the release of my mystery commercial plug-in. I had a few ideas, none of which were feasible within three months, but certainly nothing that really grabbed me.

Then, while working on a Shimmer reverb algorithm (yes, the kind that feeds the reverb signal into a pitch shifter set an octave higher, popularized by Brian Eno, U2, and Valhalla's plug-in), I found myself having fun trying to sustain the feedback loop for as long as possible. I added various effects that could be tweaked in real-time, like dynamic compression to keep the output from exploding, until it felt less like using a mere effects box and more like playing an actual instrument.

I was also significantly influenced by a few recent personal sonic adventures in electronic music, which I'll have the chance to tell you more about later, that helped inspire, among others, a friend and ambient music composer, the artist [Almost Random](https://www.almostrandom.fr/), who has just released a [new album](https://cyclicaldreams.bandcamp.com/album/fragments-from-the-waning-world-cyd-0163) on [Cyclical Dreams](https://www.cyclicaldreams.com/).

![Prototype]({{site.baseurl}}/images/VoyageVoyage-0.2.0.png)

In any case, that was the moment it clicked for me; I felt the need to turn these experiments into something concrete, seizing the opportunity provided by the contest to also work on the elements I mentioned earlier. The project's name came later, I liked its "French" ring, and I immediately envisioned moving between the Korg "Submarine" reverb (found in the Logue series) and the "Riser" and "Space" reverbs (specifically the -12 and +12 Shimmer settings, which sound fantastic), which also inspired the graphic design you're familiar with. The trouble was, the first prototype I had on hand was nowhere near good enough for a commercial release, and it was already early June when I made these decisions. I had just one month to see the project through to completion, on top of my regular job!

## Product Design & Automation

So, I kept working on the concept-focusing first on the sound, of course, but also on the controls I'd make available to the user. I spent time figuring out exactly what that #j$&@ Chaos control would do, it kept changing right up to the last minute, and addressing the low-frequency heavy content, which gave me trouble early on and needed to be tamed as much as possible. I then spent a few hours looking for graphic design inspiration in the hardware world, specifically Erica Synths pedals (which fit perfectly with their existing lineup of FX and instruments), but also drawing ideas from various delay and reverb units, and even other instruments, that I really like.

At the same time, I wanted something that wasn't just another "Shimmer" reverb; I wanted to add a unique twist, which, as you've guessed, turned out to be the self-oscillation and drone generation features. I tried to make this as fun as possible, even though the workflow is unconventional, requiring you to regularly record the plug-in's output rather than just relying on automation to get the best results, and I needed the GUI to reflect that aspect. I also figured this would help the plug-in stand out from recent market releases.

![Design attempts]({{site.baseurl}}/images/VoyageVoyageGraphicDesign.png)

Some other aspects of the design I tried to focus on:

- I didn't want my Shimmer effect to sound generic or even cliché
- I wanted something with personality and control, specifically over the Shimmer delay length, which allows for adjusting the build-up that is often fixed in this category of effects
- I took the time to determine which potentiometers should be highlighted, and considered factors such as their placement on the interface and the use of different sizes and concepts
- Various elements needed to encourage users to experiment with the drone and instrument sections of the plug-in, by eliminating friction with the UX, gently prompting them to explore, whether through built-in tutorials, color-coding, preset categories choice, and so on
- Finally, I wanted the sweet spots to be accessible with a minimum number of operations, so I had to merge controls or turn some of them into macros that affect multiple internal parameters.

And fortunately, I was very quickly very happy about the way it sounded, and it made me want to create interesting music with it, something I tried to demonstrate with the audio demos I released (with the help of [Olivier VM](https://soundcloud.com/ovehem)).

<iframe width="100%" height="300" scrolling="no" frameborder="no" allow="autoplay; encrypted-media" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/playlists/soundcloud%253Aplaylists%253A2264558060&color=%23ff5500&auto_play=false&hide_related=true&show_comments=false&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/musicalentropy" title="musicalentropy" target="_blank" style="color: #cccccc; text-decoration: none;">musicalentropy</a> · <a href="https://soundcloud.com/musicalentropy/sets/voyage-voyage-audio-demos" title="Voyage Voyage audio demos" target="_blank" style="color: #cccccc; text-decoration: none;">Voyage Voyage audio demos</a></div>

Anyway, things started to take shape, and then I really had to nail down the layout, choosing the final controls, the interface arrangement, sizes and positions, and DSP interactions, as well as the graphics. I'm very confident about the coding side of things, having worked in this field for decades. This experience has given me both the know-how to create new things and a reusable codebase-covering elements like plug-in parameters, basic DSP blocks, and preset systems, that I've already automated through my previous freeware projects, allowing me to bypass AI entirely. 

On the graphics side, however, the timing leading up to the deadline started to worry me a bit... I have solid skills in Affinity Photo, Knobman, and Blender 3D, but I've been procrastinating on redesigning the GUI for *Spaceship Delay* for years; I remember being frustrated when it was first released because I hadn't had the time to fully realize my aesthetic vision. I wasn't sure I could pull it off for Voyage Voyage.

I had actually started working on a project to automate plug-in design, which, unfortunately, wasn't finished yet, as well as on categorizing an element I find fascinating: hardware knobs and, of course, their software counterparts when using a skeuomorphic aesthetic. I came across a [pretty interesting article](https://www.guitarpedalx.com/news/gpx-blog/pedal-design-101---all-about-pedal-knobs-and-why-more-brands-should-have-their-own-signature-versions) featuring the image you see below (can you guess which ones I used?).

![Knobs categories](https://d6a2e7ghqts3o.cloudfront.net/AcuCustom/Sitename/DAM/513/2019GPXPedalKnobs700V2.jpg)

Finally, and let's be very clear about this right from the start, the graphic design for *Voyage Voyage* is the result of my work in Affinity Photo, involving layers of diverse materials and the use of the venerable Knobman3D for the potentiometers. I had a very personal vision for the design that evolved through iteration; I incorporated some reworked, royalty-free assets from the web, a drawing by my daughter that I vectorized, and some AI-generated abstract elements for the pedal's background, something I recently discussed over at [Bedroom Producers Blog](https://bedroomproducersblog.com/2026/07/29/musical-entropy-voyage-voyage/). I also briefly tested the capabilities of certain paid AI models while I was learning the ropes. I quickly realized that the results I was achieving on my own were great, and way more satisfying in every respect, even with my current skill level!

![Space Cat by LC]({{site.baseurl}}/images/OriginalSpaceCat.png)

While wrapping up the project, I took the opportunity to refine a few features I'd wanted to include in my plug-ins for a while: the resizing strategy, improvements to the preset system, and new Easter eggs, specifically one utilizing Roland Rabien's JUCE module [gin_controllers](https://github.com/FigBug/Gin), which I reworked to support all types of joysticks, as well as a feature that simulates kicking a spring reverb unit!

I also took a look at **JUCE's accessibility features**, integrated into the core modules since version 6.1 and compatible with Narrator on Windows and VoiceOver on macOS, by adding descriptions for each control and quickly testing how the plug-in operates with these tools. I also checked visual accessibility using the "Colour Simulations" tool on Windows. The resulting image for deuteranopia suggests I still have some work to do on my graphic design, but it will be completed on version 1.1.

![Rendering simulation for people with color blindness]({{site.baseurl}}/images/VoyageVoyage-ColourSims.png)

So I'm very happy to have seen this plug-in project through to completion, regardless of the contest outcome, and I fully intend to keep talking about it and adding a few more features after the competition ends. I also hope you enjoyed my long post! If you liked my work and my explanations, please feel free to download the plug-in and vote for it, as well as for the work of the other developers participating in the [KVR Audio Developer Challenge](https://www.kvraudio.com/kvr-developer-challenge/2026/). You might also notice that I've done a bit of cleanup on my two websites (here and at musicalentropy.com).

[Voyage Voyage by Musical Entropy](https://musicalentropy.com/VoyageVoyage.html)

Stay safe!
