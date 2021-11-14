---
title: Debugging Harley LiveWire Bluetooth and iPhone Issues, Part 1
---

TLDR: If at first you don't connect, try, try and sometimes try again. I found my LiveWire would only connect to my phone roughly half the time, and waiting beyond 30 seconds for it to connect is unlikely to help.

I'm determined to uncover as much as I can as to what is undermining the Bluetooth connection between my new iPhone 12 Pro Max and my new Harley Davidson LiveWire electric motorcycle. It's my thing -- iOS and hardware, after all.

For this post, I decided to focus on a simple experiment. How often (and how quickly) does the phone connect to the bike when I power on the bike?

The results were kinda shocking honestly.

For the experiment, I placed my iPhone 12 Pro Max running iOS 14.7.1 on the seat of the bike. My Harley is running software version 01.02.00-02. My security fob was nearby, although not super close -- it was in my thigh bag about 2m from the bike.

The only other devices connected to my phone were a Ford Mach-E and my Apple Watch.

I turned on the bike and started a stopwatch and waited to see how long until the Bluetooth indicator on the Harley turned from gray (not connected, see below) to blue (connected, see below.) If 90 seconds had passed, I gave up waiting and turned off the bike. If it did connect, I'd note the time, turn off the bike, and wait for the iPhone Settings > Bluetooth screen to also show it "Not Connected."

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679290808/in/dateposted-public/" title="hdlw_1_not_connected"><img src="https://live.staticflickr.com/65535/51679290808_730facb354_o.jpg" alt="hdlw_1_not_connected"></a>

*Bluetooth Not Connected (Gray Icon, Top Left)*

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679290778/in/dateposted-public/" title="hdlw_1_connected"><img src="https://live.staticflickr.com/65535/51679290778_4911ed2d7b_o.jpg" alt="hdlw_1_connected"></a>

*Bluetooth Connected (Icon Turns Blue)*

If the bike didn't connect, I'd wait until I heard the last relay click inside before during it back on, about 10 seconds or so (I
didn't measure this exactly.)

I repeated this 20 times.

9 out of 20 times it never connected. 11 times it did, but the time it took to connect varied quite a bit.

8 times out of 20 it connected in 24 seconds or less -- the other three times it took 30, 35 and 44 seconds

And it isn't as simple as waiting for 90 seconds turning it off and then getting it to connect. Twice it failed to connect 3 times back to back. Oooof.

So, the Traction Control and ABS lights toggle on, off and on again about every two second. They appear about 10 seconds after turning
on the bike. One thing I'll probably do until I sort this out is count 7-8 blinks and, if the Bluetooth hasn't connected by then, turn off the
bike and try again. Meh.

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679035181/in/dateposted-public/" title="hdlw_1_shield"><img src="https://live.staticflickr.com/65535/51679035181_331270e9a4_o.jpg" alt="hdlw_1_shield"></a>

*Boot Up H-D Shield. If Bluetooth doesn't turn connect within about 15 seconds after this disappears, chances are it won't.*

And something else peculiar came up during the experiment.  Multiple instances of my LiveWire in Other Devices (see screenshot below). I'll
probably throw together a little app to see why that's happening. iOS Settings > Bluetooth just shows the device name there.

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679920960/in/dateposted-public/" title="hdlw_1_bluetooth"><img src="https://live.staticflickr.com/65535/51679920960_2a02c53bbb_o.jpg" alt="hdlw_1_bluetooth"></a>

Stay tuned!

Edit: Part 2 is now up and includes easy-to-follow steps to get your LiveWire Bluetooth pairing to work successfully.
