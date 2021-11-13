---
title: Setting Up iOS Bluetooth PacketLogger in Xcode
---

Edit (Oct 2, 2021): I later found a similar article on the Bluetooth SIG website



iOS has two ways to see Bluetooth packets. One involves capturing a log file by triggering sysdiagnose and the other allows for live capture &#8211; you can see the announcement in “What’s New in Core Bluetooth” from WWDC 2019, especially “how to debug your Core Bluetooth communication with the improvements to PacketLogger” https://developer.apple.com/videos/play/wwdc2019/901



Either way (logged or live), you’ll first need to install a “logging profile” on your iOS device before you can proceed. To do so, navigate to https://developer.apple.com/bug-reporting/profiles-and-logs/ and scroll down to “Bluetooth for iOS.” Click on the Instructions link and log in with your Developer account if needed. Follow the instructions to install the logging profile to your iPhone. Note that the profile will expire after three days.



When installed properly, it will appear under Settings &gt; General &gt; VPN &amp; Device Management, e.g.:







Tapping on the profile reveals additional details:







Connect your iPhone to your MacBook if you haven&#8217;t already.



Next, you&#8217;ll need to set up live logging with Xcode.



Live logging is provided by PacketLogger, which is not bundled with Xcode by default. To get PacketLogger, navigate to https://developer.apple.com/download/all/?q=for%20Xcode and search for the “Additional Tools” download link for your version of Xcode (e.g. 12.5), and download and open the dmg file. To get a specific tool to appear under Xcode &gt; Open Developer Tool, copy it into /Applications/Xcode.app/Contents/Applications. Don’t copy or create any folders there &#8211; Xcode won’t be able to open those from the menu. You’ll want to copy the individual tools you want to appear on the menu one at a time.If you had Xcode open, you’ll need to restart it to see the tool(s) you’ve added.



You can then access PacketLogger from the Xcode menu, ala:







And then you’re in! Live logging kicks off automatically:







Happy Bluetooth Debugging!
