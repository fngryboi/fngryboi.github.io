---
layout: post
title: Dusting Off Old Projects...
categories:
  - blog
published: false
---

It's been a long summer break, and I've actually not delved too much into developing. Mostly due to a pretty intense period of programming during the very end of the school year, which left me burned out and uninspired to do any programming in general. However, with school about to start and me looking through the abstracts of the new courses that I'm about to attend, there's been a new surge of energy and I'm very eager to create new stuff and learn new things. This first term will go into C++ and later on we'll also get 3D modeling and 3D programming (DirectX) to mention those that peaked my interest the most.

But, that's just a small update on what's been going on, which is also why I've had a mental block of sorts when it comes to posting here, however, this post is about some old tech projects I've been working on way back. Unfortunately they got put aside as other things needed my attention (and money...), that all ends today - as I have decided to dust them off and give them some love again.

### iPod Modernized

![My iPods current state](http://i.imgur.com/vJkOoK3.jpg)

*Current state of my iPod, looking very sad being unused, the logic board currently installed is the 6th gen and the 5th gen board with the Msata adapter is next to it.*

Last year I bought an iPod 6th gen, which I enjoyed using quite a lot. Although as time went on there were some gripes I had with it. First of all it was very slow, after all it relied on a 1.8" spinning hard drive, which made all the menus slow (especially if you had a huge library, which after all was the point with the iPod). Second of all, after reading online I found that the DAC built-in on the 6th gen iPod is considered the worst of all the iPods (at least this type of iPod), allegedly the best ones are the ones that had the Wolfsen DACs (generation 5.5 and earlier). Thirdly and lastly, it didn't have support for lossless formats such as FLAC.

So I set about doing intense research and buying an array of different things to upgrade the hardware. I bought a 250GB Msata SSD with a ZIF-to-Msata adapter, a new housing (6th gen with the thick back), a bigger battery (because what-the-hell), and the logic board that used to be inside a 5th gen iPod. At this point I've spent a fair bit of money, and having tons of issues with making this work.
I broke the new battery's ribbon cable, so I had to get a replacement. I don't think the ZIF-to-Msata adapter works with the iPod because nothing is showing up (white screen with no info on it), might also be the ribbon cable not working... I'm having trouble maintaining a connection to the iPod over USB. However I could re-use the screen from the 6th gen iPod as those generations had interchangeable screens.

After a while, I just got fed up with it and moved on with the intention of getting back to it some day... That day turned out to be almost a whole year later. This time however, I'll be better prepared. Below is a list of items I might be or will buy to finish this project:

1. [New 30-pin-to-USB cable](https://www.amazon.co.uk/Certified-ACEPower-Charging-generations-Packaging/dp/B00ONIBB9E/ref=sr_1_5?ie=UTF8&qid=1503442987&sr=8-5&keywords=30-pin+usb) To be sure the cable works.
2. [A new metal backplate, no logos or information, plain chrome (Thick)](http://www.ebay.com/itm/Thick-Chrome-Metal-Back-Backplate-Blank-for-Apple-iPod-Classic-6th-Gen-160gb-/172150359524?hash=item2814f605e4:g:30QAAOSwTuJYwtv3)  [Same but thin](www.ebay.com/itm/Thin-Chrome-Blank-Metal-Back-Backplate-Housing-for-iPod-Classic-80gb-120gb-160gb-/182070897656) Still undecided if I'm going with the thick or thin profile. It's all down to how thick it becomes with all the new stuff in there when it's working.
3. [iPod Audio Capacitor ByPass Kit](https://www.iflash.xyz/store/audio-capacitor-bypass-kit/) Still undecided, allegedly makes for better audio quality. But for the price I think I'll go with it.
4. [New HDD Ribbon Cable](https://www.iflash.xyz/store/hdd-ribbon/) Just to be sure the ribbon cable isn't broke.
5. [New Msata adapter](https://www.iflash.xyz/store/iflash-sata/) This one is guaranteed to work.

Lastly if all goes well, it comes down to the software. This part I'm still considering all the options I can go with, I can either flash Rockbox onto the iPod. Which will give me support for FLAC and other lossless formats and a bunch of more amazing features, but I still like the standard iPod OS it comes with. Especially for Audiobooks and Podcasts as it's nicely integrated into iTunes (but iTunes is still terrible on Windows). There is a potential option here though, but it seems to only work on 6th gen iPods or newer ([Dual-booting on iPod](https://www.reddit.com/r/rockbox/comments/48h43q/ysk_you_can_dualboot_rockbox_and_apple_os_on_an/)). Alternatively there might be plugins for Rockbox that makes the experience a little better as well, although I haven't delved into those yet... But I'll make up my mind about this whenever I get the iPod actually working again, that's the first step.

### Portable Raspberry Pi Emulator

![Current state of my portable Raspberry Pi emulator](http://i.imgur.com/DRMLYMq.jpg)

*Current state of my Portable Raspi Emulator, where you can see how I changed a SNES controller, the Raspi under the screen - which I desoldered one of the USB hubs to move it below to connect the controller, and a battery bank that's taken apart.*

This is my second project that was actually started around the same time as the iPod, however - this one is actually fully functional technically. It's just the housing of all the parts that has been stalling this project. What I've done on the housing so far is a block made out of Epoxy resin mixed with green glowing powder, with pieces of wood placed inside. With the end goal of cutting through this block into a thin layer that will make the front, the problem however is that I don't have the right tools to do this. Then for the sides and back I thought I'd go with clear plexiglass, so you can admire the technology inside.

It's built using these parts:
- Raspberry Pi 3 Model B
- 3.5" Adafruit PiTFT screen, although the smaller one is said to have better refresh rate. But I'm not so picky, the whole display unit is the same size as the Raspberry Pi and connects using the 40 GPIO pins and a small software tweak to make it work.
- Knock-off SNES USB Controller, which I cut the board in half and soldered all the connections back together and then put them vertically to make the whole unit into a Gameboy Color shape.
- An external battery bank with 10,000 mAh capacity, not yet tested how long it runs for but I've had it running for more than 4h at the very least from one charge so it should be sufficient. I took it apart from the original case so everything is currently exposed. The case will probably protrude a bit where the battery is, which is okay since I'm planning to put the shoulder buttons alongside the protrusion from the case.
