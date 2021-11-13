---
title: Debugging Harley LiveWire Bluetooth and iPhone Issues, Part 2
---

TLDR: So&#8230; like others, I am unable to use iOS Settings &gt; Bluetooth to pair my Harley-Davidson LiveWire&#8230; the motorcycle doesn&#8217;t even appear (making it impossible to pair with) or if it does appear, pairing usually fails. However, I have been able to successfully pair using the LightBlue app by Punch Through &#8211; its a developer tool for debugging Bluetooth connections &#8211; and once paired, it stays paired (thankfully, although it sometimes takes a few power cycles of the bike to get it to connect &#8211; see Part 1 for details). Anyways&#8230; this post tells you what you need to know to get the LiveWire to pair. (You can find Part 1 of this series here.)



I&#8217;m digging deep into what&#8217;s going on with iPhone Bluetooth pairing and re-connection problems with the Harley-Davidson LiveWire, but in the mean time I&#8217;ve found a solid workaround for the pairing part. You can read about Part 1 of my investigations here and a future post (hopefully not as far in the future as this one turned out to be) will dig more into what I&#8217;m seeing at the packet and radio level.



In the meantime, here&#8217;s how to get it to pair if you are having no success pairing in iOS Settings &gt; Bluetooth.



First, get the LightBlue app by Punch Through on your phone. It&#8217;s an excellent developer tool that I suspect uses a different set of scanning parameters than iOS does in Settings.







Once you&#8217;ve installed that, enable pairing on your LiveWire by going to Settings (the Gear icon) &gt; System &gt; Bluetooth &gt; Pairing. Your screen should look something like this:







On your phone, open the LightBlue app and enter &#8220;HD&#8221; in the search box to make finding the LiveWire faster:







Tap on your bike&#8217;s name (mine is HD-CA4B &#8211; maybe everyone&#8217;s is) and you&#8217;ll then see:







And then, after a few moments &#8211; the pairing request confirmation dialog should display. Tap on Pair:







If you get this prompt, I recommend tapping on Allow &#8211; although honestly I don&#8217;t think the LiveWire displays these at this time:







And then&#8230; that&#8217;s it! It&#8217;s a little anti-climactic in the LightBlue app, but you&#8217;re all set at this point:







You should now see this on your bike (fingerprints and all, LOL):







And don&#8217;t forget to try the navigation and audio widgets that Bluetooth unlocks:







Enjoy! Don&#8217;t forget to wipe the fingerprints off your display.



In the next post, I&#8217;ll dig into some of the things I&#8217;ve learned about the Bluetooth transceiver on the bike and some of the things I&#8217;m seeing in PacketLogger on iOS. I&#8217;m determined to figure out why the Bluetooth discovery and pairing performs so poorly on this bike.



Thankfully, once connected the connection seems pretty solid &#8211; so I can use the handle bar controls to skip songs and pause and resume. I&#8217;ve not used the H-D Connect navigation much yet, but I&#8217;ll give that some proper use on upcoming rides too.
