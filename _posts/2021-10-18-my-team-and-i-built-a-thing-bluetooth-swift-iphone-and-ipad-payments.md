---
title: My Team and I Built A Thing Bluetooth plus Swift equals iPhone and iPad Payments
---

TLDR: In-Person Payments for WooCommerce is Live



A few years back, I drafted an unusual multi-year proposal for my small team at Automattic (the parent company of the open source DIY e-commerce platform known as WooCommerce ) &#8212; that we would integrate hardware into our apps and systems so our online merchants could expand into in-person payments. That same year my team and I launched a shipping labels printer integration with EasyPost and the United States Postal Service (USPS) optimized for the USB based Dymo LabelWriter 4XL. Now I am happy to announce another piece of hardware...



Today we launch In-Person Payments for WooCommerce Payments - allowing our merchant to get started with in-person card payments with an affordable, simple, super portable Bluetooth card reader backed by Stripe 🙂 It looks like this:

<img src="https://live.staticflickr.com/65535/51677164402_7554782104_k.jpg"/>

I pivoted from an engineering manager and team lead to an engineer again to focus on the technical challenges of integrating the Bluetooth readers and Stripe’s Terminal SDK with iPhones and iPads using Swift. My team and I have been working closely with Stripe engineering on this all year long and today I am happy to say we are opening it up this week to any merchant in the US.



We’ve started with Stripe’s BBPOS Chipper 2X BT Bluetooth card reader. It’s a very small headless reader with surprisingly long battery life. It has a dual Classic Bluetooth and Bluetooth LE radio, but relies on BLE to get its work done. It supports chip, swipe and NFC (tap) payments.&nbsp;



Our challenges included integrating reader discovery, connecting, multiple reader management, providing Over the Air (OTA) software updates to the reader, displaying messages in our app from the reader (again, it’s headless) and integrating all that over the Internet to Stripe, our backend and our merchants’ backends (we don’t have a single cloud backend - we don’t control much of the backend - legendary mode enabled!)







Stripe’s Terminal SDK is delivered via CocoaPods and, especially with the SDK 2 release, provides for a fairly straightforward integration with our Swift codebase. The biggest challenge in that regard is our modified Flux architecture: our stores are stateless, with the lion share of actions being triggered by the views and their viewmodels to fetch models from the backend on demand as the user navigates from page to page.







Hardware makes this more interesting as the readers can disconnect any time they want, demand software updates, need to ask the UI to display messages or switch to other users. It’s kinda like having two users at once:









We ended up having the card reader store hold a reference to a card reader service that does maintain state. It also means that service is the one in the drivers’ seat. User actions are basically limited to initiating or, when the service allows, cancelling payment collection. The service doesn’t dispatch any actions at all. It sets the state to what it wants. We’ll see if changes will be needed, but so far it has held up.



We’re also recommending a capable (although expensive) battery powered portable receipt printer from Brother - the Brother RJ-4250WB-L - it was surprising how few battery powered WiFi Direct printers are on the market. We’re supporting WiFi and WiFi direct for now, but this printer also supports Bluetooth connections and has an SDK for them, so integrating finer control of this versatile printer is an option for us. It was a pleasure working with Brother engineering with this printer selection as well.







Here’s what capturing a payment looks like, start to finish:









Net net: I’m delighted to be able to continue to work with hardware and build with Swift again at what is almost exclusively a software company. I’ll share some more in the upcoming weeks on some of the considerations and obstacles we had to overcome to integrate this into our iOS app, our operations and the backends.



I can happily say that working with Stripe on this made it easier. Their documentation is superb and their engineering support is outstanding. We had to also work out a few things with Apple (to avoid the merchant’s iPhone attempting to pay for the purchase if the reader was too close to an iPhone with Apple Wallet set up) and that went fairly smoothly too (if slower).



If you’re interested in accepting in-person credit card, debit card and digital wallets with a backend you largely host and manage yourself, take a peek here: https://docs.woocommerce.com/document/getting-started-with-in-person-payments-with-woocommerce-payments/



If you’re interested in seeing the Swift code and work involved in integrating with Stripe Terminal’s SDK and Bluetooth card readers like the Chipper, you can see my contributions and the rest of the team’s work here: https://github.com/woocommerce/woocommerce-ios



And... if you’re looking, we’re fully remote (another challenge for hardware work) and hiring https://automattic.com/work-with-us/! We have open positions for senior engineers on both our iOS and Android e-commerce apps https://automattic.com/work-with-us/job/senior-mobile-engineers-woocommerce-android-ios/
