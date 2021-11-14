---
title: Debugging Harley LiveWire Bluetooth and iPhone Issues, Part 2
---

TLDR: So... like others, I am unable to use iOS Settings > Bluetooth to pair my Harley-Davidson LiveWire... the motorcycle doesn't even appear (making it impossible to pair with) or if it does appear, pairing usually fails. However, I have been able to successfully pair using the LightBlue app by Punch Through - its a developer tool for debugging Bluetooth connections - and once paired, it stays paired (thankfully, although it sometimes takes a few power cycles of the bike to get it to connect - see Part 1 for details). Anyways... this post tells you what you need to know to get the LiveWire to pair. (You can find Part 1 of this series here.)



I'm digging deep into what's going on with iPhone Bluetooth pairing and re-connection problems with the Harley-Davidson LiveWire, but in the mean time I've found a solid workaround for the pairing part. You can read about Part 1 of my investigations here and a future post (hopefully not as far in the future as this one turned out to be) will dig more into what I'm seeing at the packet and radio level.



In the meantime, here's how to get it to pair if you are having no success pairing in iOS Settings > Bluetooth.



First, get the LightBlue app by Punch Through on your phone. It's an excellent developer tool that I suspect uses a different set of scanning parameters than iOS does in Settings.







Once you've installed that, enable pairing on your LiveWire by going to Settings (the Gear icon) > System > Bluetooth > Pairing. Your screen should look something like this:







On your phone, open the LightBlue app and enter "HD" in the search box to make finding the LiveWire faster:







Tap on your bike's name (mine is HD-CA4B - maybe everyone's is) and you'll then see:







And then, after a few moments - the pairing request confirmation dialog should display. Tap on Pair:







If you get this prompt, I recommend tapping on Allow - although honestly I don't think the LiveWire displays these at this time:







And then... that's it! It's a little anti-climactic in the LightBlue app, but you're all set at this point:







You should now see this on your bike (fingerprints and all, LOL):







And don't forget to try the navigation and audio widgets that Bluetooth unlocks:







Enjoy! Don't forget to wipe the fingerprints off your display.



In the next post, I'll dig into some of the things I've learned about the Bluetooth transceiver on the bike and some of the things I'm seeing in PacketLogger on iOS. I'm determined to figure out why the Bluetooth discovery and pairing performs so poorly on this bike.



Thankfully, once connected the connection seems pretty solid - so I can use the handle bar controls to skip songs and pause and resume. I've not used the H-D Connect navigation much yet, but I'll give that some proper use on upcoming rides too.
