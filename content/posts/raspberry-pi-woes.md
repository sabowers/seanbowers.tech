---
title: "Raspberry Pi Woes"
date: 2023-07-04T23:01:32-07:00
draft: false
authors: [Sean Bowers]
tags: [Raspberry Pi, Nextcloud, Ubuntu, LAMP]
---
I had five days off—two for a wedding, two for my regular weekend, and the 4th of July. I decided that this would be a great time to finally migrate my Nextcloud to my new Raspberry Pi case, the (Argon One)[https://argon40.com/products/argon-one-m-2-case-for-raspberry-pi-4] . I was excited to pull my personal cloud off of (Digital Ocean)[https://www.digitalocean.com/] and into my home. That is not to say that I wasn't pleased with the service they have at Digital Ocean, I actually enjoyed my time there quite a bit. But I would much rather not have to pay a host fee, as well as retain full control over my data. 

With that, I figured I would try my hand at the new Nextcloud AIO Docker image as a means for learning Docker. Let's just say running Docker on a Pi, or anything for that matter, isn't a one-for-one experience to what I am use to on Arch Linux. Not sure why I blindly assumed that it would be. So after cloning and recloning my microSD card and SSD for a day and a half, and decided I would do it the old fashion way, and spin up a LAMP stack server. Plus, it would be nice to get the practice. 

Well, what I didn't anticipate was trying to build out currently-developed software might possibly neccesitate more than a 32bit Raspberry Pi OS. This one took me a while, as I have historically been an Arch Linux user and have bristled with antagonism at some of the packages on Debian-based systems. So it didn't surprise me that I couldn't find an up-to-date PHP package. However, I didn't think the problem could be that I was running a 32bit OS. 

So going back to the drawing board, I learned that Ubuntu has a 64bit ARM image (again, not sure why this wasn't obvious to me). So I figured I would just put Ubuntu on my Pi. After struggling with switching back and forth between Windows and Linux machines flashing microSD cards (both Balena Etcher and RPI Imager packages don't quite work correctly as is from the Arch repos), I finally got it up and running. Cloned the the microSD to the SSD and got to work. Got the LAMP stack up and running, and began the treacherous adventure of getting access to the router for port forwarding in a house filled with people who have no idea what the password is. After a few hours, I tried the default and lo-and-behold, I finally got access to our terrifyingly vulnerable router. 

But it was at this that I noticed something. For some reason (definitely my fault), I was still running off the microSD card and hadn't switched over to the SSD. So all the work had been on the microSD, which was not going to stay in the machine. I tried cloning again, but got obscure errors that I was out of enough bandwidth to try to troubleshoot at this point. I could have thrown my machine through the window. And seeming I was still too unsure how or if I could fix the issue, I figured I would just start from scratch. So I flashed the SD card again (not sure why) and went to turn it on and found myself staring at an "initramfs" prompt. After staring in shock, for what seemed a decade, I tried 5 minutes of troubleshooting and resolutely turned the machine off. 

And with a sigh of resignation, I got some delicious vegan ice cream out of the freezer and sat back down to watch some Star Trek Discovery. 

Some days, or weeks, you just can't win.

