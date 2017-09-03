---
layout: post
title:  "Diving into the Hackintosh"
date:   2017-09-03
featured_image: hackintosh.png
tags: [tonymac, hackintosh, sandy bridge, osx, windows]
---

Today I'm writing about the Hackintosh and the community around it - a place where people have spent many hours reverse-engineering Apple's macOS kernel with the grand goal of making it run (with native speed) on Windows or Linux-based hardware.
<!--more-->

### Sacha's Takeaways

* Building a solution to a seemingly impossible problem, no matter how small the impact, is extremely rewarding
* You can get performance similar to or greater than the highest end Mac Pros ($12,000+) for less than $4,000 by building the rig yourself, and dual-booting Windows / macOS
* For those of us who develop for different platforms, having the ability to switch to and from macOS (to build for iOS, for example), while maintaining expected speed, is a huge productivity boon.

### Full Text

The first time I heard the term "Hackintosh" was back in 2010 - when OSX Snow Leopard was the "next big thing" and [Universal Binaries](https://en.wikipedia.org/wiki/Universal_binary) were everywhere as Apple was mid-migration from the PowerPC architecture to the more mainstream x86_64 Intel instruction set. I was in high school, and had a few friends who spent too many hours trying to get their PCs to run Mac so that they could do 4-person video iChats with their cooler, Mac-owning friends. 

Unfortunately for them, many motherboards/systems were "bricked" in vain attempts to get OS X to boot. Nothing was really permanently broken, but we were in high school, therefore lacking much of the debugging knowledge and experience we have now. Suffice it to say the parents were not pleased. 

{% include image_full.html imageurl="/images/posts/kp.jpg" title="No company has ever made a kernel panic look so good." caption="No company has ever made a kernel panic look so good." %}

The fear of "bricking" my machines tempered my interest and passion to solve this problem for a few years, but as I spent more time coding, learning about system architecture, and becoming more conformable working with the kernel, I gradually began researching. 

For those unfamiliar, the go-to place for anything Hackintosh-related is [tonymacx86](https://www.tonymacx86.com/). There you can find installation guides, debugging tools, build results, and a wealth of experts with more experience dealing with extremely arcane problems than you could ever imagine. One of the most important things you'll see upon browsing through their forums is that the hardware you own is a key determinant of how successful your Hackintosh build will be. Unfortunately (or fortunately?) for me, I built my current machine in late 2011, so when I went to tonymac earlier this month to do some preliminary research, I found very little content related to the components I own. For reference, I'm running an i7-3930k Sandy Bridge-E CPU on an ASUS P9X79 Deluxe motherboard. More details can be found at the build link below.

{% include image_full.html imageurl="/images/posts/p9x79.jpg" title="The P9X79 Deluxe." caption="The P9X79 Deluxe." %}

Because there was no "one stop shop" solution to how to get macOS on my now 6-year old machine (I can still run most games/apps at max settings somehow), I decided to experiment with different settings and ideas for a couple days. Back in high school when I first looked into the Hackintosh, this would have been extremely dangerous. If I hit a kernel panic (KP), I would have been completely hosed. But now, comfortable with unix and log digging, I thought - why not? Long story short, I did actually break my bootloader, Windows OS, and sent my machine into an unbootable cycle. Overconfidence is indeed deadly.

This wasn't an entirely bad thing - I had the chance to start fresh. I grabbed a new Samsung 850 EVO SSD from Amazon Prime Now (apparently you can now order computer parts and have them delivered to you in less than an hour...) and decided to install each OS on a different drive rather than partition a single one.

Three days of work later, and I'm writing this blog post from [Visual Studio Code](https://code.visualstudio.com/) on Mac, with streaming TV on a second monitor and some games open on the third. The machine is whirring away at full speed and I've had no issues. 

Let's chat a little bit about that three day span I just glossed over. 

>Making a Hackintosh work is a bit like putting together a 2,000 piece puzzle that completely falls apart if you incorrectly put in one small tile.

Think of each major function your computer provides as a subsection of pieces - you have audio, networking, CPU, GPU, Bluetooth, WiFi, USB, SATA (storage), and more. But that's not it - since we are basically impersonating a Mac to Apple (aka Big Brother), many software features we take for granted also need to be addressed - iMessage, FaceTime, Handoff, iCloud, etc.

{% include image_full.html imageurl="/images/posts/clover.png" title="Impersonating a Mac via Clover Configurator." caption="Impersonating a Mac via Clover Configurator." %}

I was able to get Mac "running" quite easily - the tooling provided on tonymac is very good for the initial setup of a computer, but getting things to run at full speed was much harder. I won't repeat the entire build process here, but you can find my installation guide [here](https://www.tonymacx86.com/threads/success-10-12-6-p9x79-deluxe-i7-3930k-w-turbo.230926/) with specific links to extra steps needed to get Audio, iMessage, and full CPU speed working. 

When sharing this arduous procedure with friends, the most common reaction I got was "I don't understand why people spend so much time on these things". To be completely honest, I don't have a great answer for that. There are many (better) things I could have done with a holiday weekend, but something about getting everything to the working state I have now is insanely rewarding.

>There is great benefit in working at a seemingly impossible problem, regardless of impact, and coming through with a viable solution. 

Six years of waiting and exploring came full circle today. Thanks for reading, and as always, feel free to reach out to me with any questions, or if you are considering trying your hand at a Hackintosh build. 
