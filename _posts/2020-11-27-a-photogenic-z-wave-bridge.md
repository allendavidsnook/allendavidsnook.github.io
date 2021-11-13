---
title: A Photogenic Z-Wave Bridge
---

We&#8217;re moving away from Z-Wave tech and investing more deeply in Apple HomeKit. Part of that will include using a Raspberry Pi to act as a Z-Wave bridge until we (eventually) replace the Z-Wave devices with devices supported by HomeKit natively.



And because it would be boring just to plugin in a headless Raspberry Pi, I decided to have it do double duty as a digital picture frame using a neat little touchscreen by EVICIV.



This article covered most of the setup needed to use feh and xscreensaver, although I did need to do one tweak, probably because I am running a relatively new version of Raspbian (Raspbian GNU/Linux 10 (buster)) that was released after the article. Instead of finding the autostart file in ~/.config, it was in /etc/xdg/lxsession/LXDE-pi



Here&#8217;s what it looks like:







Yeah, I should put some real photos in there, not memes 🙂
