---
title: Custom Kernel in Linux
author: Chris Titus
type: post
date: 2019-09-29T00:32:45+00:00
url: /custom-kernel/
image: /wp-content/uploads/2019/09/customkernels-300x169.jpg
categories:
  - Linux
tags:
  - Linux Kernel
---
This Guide walks your through how to install a custom kernel on Linux. I will go over performing this in a Debian-based system and an Arch-based system. Please note that the arch based system requires you to build the kernel yourself and will take much longer. <!--more-->

Custom kernels in Linux are based on the Zen project and have some workstation/desktop optimizations. They are **NOT** meant for server installations. These are meant for those using Linux Desktop and utilizing it for Gaming, Production, etc. and overall I don&#8217;t recommend using these. However, if you like to tinker and squeeze every bit of performance out of your kernel than you can proceed.

![debian](/wp-content/uploads/2019/09/debian.svg) 

## Custom Kernel on Ubuntu / Debian / Mint / Pop OS

_Official Site [https://liquorix.net/](https://liquorix.net/) for the Liquorix Kernel._

**Vanilla Debian** requires a bit of a long command to install the custom kernel, but works fine.

`codename="$(find /etc/apt -type f -name '*.list' | xargs grep -E '^deb' | awk '{print $3}' | grep -Eo '^[a-z]+' | sort | uniq -c | sort -n | tail -n1 | grep -Eo '[a-z]+$')" && sudo apt-get update && sudo apt-get install apt-transport-https && echo -e "deb http://liquorix.net/debian $codename maindeb-src http://liquorix.net/debian $codename main# Mirrors:## Unit193 - France# deb http://mirror.unit193.net/liquorix $codename main# deb-src http://mirror.unit193.net/liquorix $codename main" | sudo tee /etc/apt/sources.list.d/liquorix.list && curl https://liquorix.net/linux-liquorix.pub | sudo apt-key add - && sudo apt-get update`

**Ubuntu,** **Linux** **Mint**, and **Pop** **OS**! are quite a bit shorter for the install.

`sudo add-apt-repository ppa:damentz/liquorix && sudo apt-get update`  
`sudo apt-get install linux-image-liquorix-amd64 linux-headers-liquorix-amd64`

![arch](/wp-content/uploads/2019/09/arch.png) 

## Custom Kernel on Arch Linux, Manjaro, etc.

For Arch-based systems the command to run is simplier than all of the above. However, this is **BUILDING** a kernel and on a low-end system this will take **HOURS**.   
_Example: On my AMD Ryzen 2700 with 16 threads and 8 cores, this took almost 60 minutes!_

`yay -S linux-lqx`  
_Note: This uses yay as the AUR helper. you may need to change this if you use something else like Yaourt, pacaur, trizen, etc._

For modifying which Kernel you are going to boot in check out these videos going over modifying GRUB

## Custom Boot (Grub, Rescue, and UKUU) YouTube Videos

The following videos will help you if you need to revert your kernel or setup multiple kernels to boot into your Linux installation. This is highly recommended. 

Grub Customizer: <https://www.youtube.com/watch?v=3s7qBJ-H7vw>  
Grub Rescue: <https://www.youtube.com/watch?v=r7meKJsjqfY>  
Kernel Upgrade with UKUU: <https://www.youtube.com/watch?v=fnn_MzosdwA>

## Video Walkthrough
[![custom kernel-yt](https://img.youtube.com/vi/nd0MysqLDB0/0.jpg)](https://www.youtube.com/watch?v=nd0MysqLDB0)  
_Note: YouTube Video - Hold Ctrl + Left Click to open in new window_


## Contact Me

I live stream on [Chris Titus Tech YouTube Channel][1] every Friday at 10 AM CST and archive clips to [Titus Tech Talk][2]. I also regularly publish to [christitus.com][3], but if you'd like to contact me directly or want to contribute to help keep these articles and videos being made consider joining the CTT members. 

Two Memberships exist:
- [ChrisTitus.com Members Section][4] (_CC Only_)
  - Full Archive of All Unlisted Live Streams
  - Direct Members Only Email
  - Monthly Members Only Video
  - Starting at $2 Per Month (_100% of Proceeds goes to Chris Titus Tech_)
- [YouTube Chris Titus Tech Membership][5] (_All Payments Accepted_)
  - YouTube Emojis for Comments and Live Chat
  - YouTube Badges that changes based on membership time for comments and chat.
  - All YouTube comments are highlighted when I review comments daily. 
  - Immediate Access to Full Live Streams
  - $4.99 Per Month (_70% of the Proceeds goes to Chris Titus Tech_)

 [1]: https://www.youtube.com/c/ChrisTitusTech
 [2]: https://www.youtube.com/c/ChrisTitusTechStreams
 [3]: https://christitus.com/
 [4]: https://christitus.com/members
 [5]: https://links.christitus.com/join