---
title: Debugging Harley LiveWire Bluetooth and iPhone Issues, Part 3
---

Look at what I found printed on the bottom of my LiveWire’s display unit:

<a data-flickr-embed="true" href="https://www.flickr.com/photos/allenreloaded/51679707029/in/dateposted-public/" title="hdlw_3_clues"><img src="https://live.staticflickr.com/65535/51679707029_1f711087db_o.jpg" alt="hdlw_3_clues"></a>

Two immediately interesting bits of information there -- a Harley-Davidson part number (70900801) and an FCC ID (SQGBT850).

A bit of quick googling finds 70900801 is “INSTR,CLSTR,DIGITAL” (Instrument, Cluster, Digital). There’s even one on eBay right now. Google also turns up this NHTSA copy of a LiveWire Service Bulletin from late 2019  -- which dumps a few acronyms (as an engineer, I love acronyms) on us, including “IM” (Instrument Module) as the proper name for the display unit.

But it’s that second bit of information printed on the Instrument Model - the FCC ID - that’s more useful to me however for figuring out the Bluetooth flaws. (I was surprised I could NOT find this in the motorcycle's manual, btw.)

Knowing that FCC ID (we’re doing something similar at work btw - using FCC IDs to look at the reports for various Bluetooth devices we are working with) leads me to this: Laird Connectivity Bluetooth 4.2 Dual Mode USB HCI Module, Bluetooth 4.2 Dual Mode UART HCI Module BT850 -- the Bluetooth module at the heart of the LiveWire Instrument Module.

And that page has user manuals for that module that should help me as I debug further. Stay tuned!

You can find Part 1 here and Part 2 here, btw.
