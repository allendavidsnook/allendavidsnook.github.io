---
title: Debugging Harley LiveWire Bluetooth and iPhone Issues, Part 1
---

TLDR: If at first you don&#8217;t connect, try, try and sometimes try again. I found my LiveWire would only connect to my phone roughly half the time, and waiting beyond 30 seconds for it to connect is unlikely to help.



I&#8217;m determined to uncover as much as I can as to what is undermining the Bluetooth connection between my new iPhone 12 Pro Max and my new Harley Davidson LiveWire electric motorcycle. It&#8217;s my thing &#8211; iOS and hardware, after all.



For this post, I decided to focus on a simple experiment. How often (and how quickly) does the phone connect to the bike when I power on the bike?



The results were kinda shocking honestly.



For the experiment, I placed my iPhone 12 Pro Max running iOS 14.7.1 on the seat of the bike. My Harley is running software version 01.02.00-02. My security fob was nearby, although not super close &#8211; it was in my thigh bag about 2m from the bike.



The only other devices connected to my phone were a Ford Mach-E and my Apple Watch.



I turned on the bike and started a stopwatch and waited to see how long until the Bluetooth indicator on the Harley turned from gray (not connected, see below) to blue (connected, see below.) If 90 seconds had passed, I gave up waiting and turned off the bike. If it did connect, I&#8217;d note the time, turn off the bike, and wait for the iPhone Settings &gt; Bluetooth screen to also show it &#8220;Not Connected.&#8221;



Bluetooth Not Connected (Gray Icon, Top Left)



Bluetooth Connected (Icon Turns Blue)



If the bike didn&#8217;t connect, I&#8217;d wait until I heard the last relay click inside before during it back on, about 10 seconds or so (I didn&#8217;t measure this exactly.)



I repeated this 20 times.



9 out of 20 times it never connected. 11 times it did, but the time it took to connect varied quite a bit.



8 times out of 20 it connected in 24 seconds or less &#8211; the other three times it took 30, 35 and 44 seconds



And it isn&#8217;t as simple as waiting for 90 seconds turning it off and then getting it to connect. Twice it failed to connect 3 times back to back. Oooof.



So, the Traction Control and ABS lights toggle on, off and on again about every two second. They appear about 10 seconds after turning on the bike. One thing I&#8217;ll probably do until I sort this out is count 7-8 blinks and, if the Bluetooth hasn&#8217;t connected by then, turn off the bike and try again. Meh.



Boot Up H-D Shield. If Bluetooth doesn&#8217;t turn connect within about 15 seconds after this disappears, chances are it won&#8217;t.



And something else peculiar came up during the experiment.  Multiple instances of my LiveWire in Other Devices (see screenshot below). I&#8217;ll probably throw together a little app to see why that&#8217;s happening. iOS Settings &gt; Bluetooth just shows the device name there.







Stay tuned!



Edit: Part 2 is now up and includes easy-to-follow steps to get your LiveWire Bluetooth pairing to work successfully.
