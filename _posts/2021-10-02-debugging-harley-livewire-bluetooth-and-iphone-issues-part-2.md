---
title: Debugging Harley LiveWire Bluetooth and iPhone Issues, Part 2
---

TLDR: So... like others, I am unable to use iOS Settings > Bluetooth to pair my Harley-Davidson LiveWire... the motorcycle doesn't even appear (making it impossible to pair with) or if it does appear, pairing usually fails. However, I have been able to successfully pair using the LightBlue app by Punch Through - its a developer tool for debugging Bluetooth connections - and once paired, it stays paired (thankfully, although it sometimes takes a few power cycles of the bike to get it to connect - see Part 1 for details). Anyways... this post tells you what you need to know to get the LiveWire to pair. (You can find Part 1 of this series here.)

I'm digging deep into what's going on with iPhone Bluetooth pairing and re-connection problems with the Harley-Davidson LiveWire, but in the mean time I've found a solid workaround for the pairing part. You can read about Part 1 of my investigations here and a future post (hopefully not as far in the future as this one turned out to be) will dig more into what I'm seeing at the packet and radio level.

In the meantime, here's how to get it to pair if you are having no success pairing in iOS Settings > Bluetooth.

First, get the LightBlue app by Punch Through on your phone. It's an excellent developer tool that I suspect uses a different set of scanning parameters than iOS does in Settings.

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679921185/in/dateposted-public/" title="hdlw_2_0_lightblue"><img src="https://live.staticflickr.com/65535/51679921185_06c313357c_o.jpg" alt="hdlw_2_0_lightblue"></a>

Once you've installed that, enable pairing on your LiveWire by going to Settings (the Gear icon) > System > Bluetooth > Pairing. Your screen should look something like this:

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679291023/in/dateposted-public/" title="hdlw_2_00_pair_a_device"><img src="https://live.staticflickr.com/65535/51679291023_49fe5cd0a6_o.jpg" alt="hdlw_2_00_pair_a_device"></a>

On your phone, open the LightBlue app and enter "HD" in the search box to make finding the LiveWire faster:

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51678233207/in/dateposted-public/" title="hdlw_2_1_filter"><img src="https://live.staticflickr.com/65535/51678233207_cbb8f6eb74_o.jpg" alt="hdlw_2_1_filter"></a>

Tap on your bike's name (mine is HD-CA4B - maybe everyone's is) and you'll then see:

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679035216/in/dateposted-public/" title="hdlw_2_2_interrogating"><img src="https://live.staticflickr.com/65535/51679035216_cb0da38462_o.jpg" alt="hdlw_2_2_interrogating"></a>

And then, after a few moments - the pairing request confirmation dialog should display. Tap on Pair:

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679706919/in/dateposted-public/" title="hdlw_2_3_pairing_request"><img src="https://live.staticflickr.com/65535/51679706919_b33bc27473_o.jpg" alt="hdlw_2_3_pairing_request"></a>

If you get this prompt, I recommend tapping on Allow - although honestly I don't think the LiveWire displays these at this time:

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679290903/in/dateposted-public/" title="hdlw_2_4_notifications"><img src="https://live.staticflickr.com/65535/51679290903_370b2f1269_o.jpg" alt="hdlw_2_4_notifications"></a>

And then... that's it! It's a little anti-climactic in the LightBlue app, but you're all set at this point:

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679035271/in/dateposted-public/" title="hdlw_2_5_connected"><img src="https://live.staticflickr.com/65535/51679035271_fc96e1acdf_o.jpg" alt="hdlw_2_5_connected"></a>

You should now see this on your bike (fingerprints and all, LOL):

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679035306/in/dateposted-public/" title="hdlw_2_6_connected"><img src="https://live.staticflickr.com/65535/51679035306_93e4d53fde_o.jpg" alt="hdlw_2_6_connected"></a>

And don't forget to try the navigation and audio widgets that Bluetooth unlocks:

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679290693/in/dateposted-public/" title="hdlw_2_7_widgets"><img src="https://live.staticflickr.com/65535/51679290693_c25c2f3d2e_o.jpg" alt="hdlw_2_7_widgets"></a>

Enjoy! Don't forget to wipe the fingerprints off your display.

In the next post, I'll dig into some of the things I've learned about the Bluetooth transceiver on the bike and some of the things I'm seeing in PacketLogger on iOS. I'm determined to figure out why the Bluetooth discovery and pairing performs so poorly on this bike.

Thankfully, once connected the connection seems pretty solid - so I can use the handle bar controls to skip songs and pause and resume. I've not used the H-D Connect navigation much yet, but I'll give that some proper use on upcoming rides too.
