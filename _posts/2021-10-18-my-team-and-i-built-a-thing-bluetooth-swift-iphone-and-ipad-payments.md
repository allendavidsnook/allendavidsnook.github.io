---
layout: post
title: My Team and I Built A Thing: Bluetooth + Swift = iPhone and iPad Payments!
date: 2021-10-18 16:47
author: allendav
comments: true
categories: [apple, BBPOS, Bluetooth, Brother, Engineering, Hardware, iOS Development, NFC, Stripe, WooCommerce]
---
<!-- wp:paragraph -->
<p>TLDR: <a href="https://woocommerce.com/in-person-payments/">In-Person Payments for WooCommerce is Live</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A few years back, I drafted an unusual multi-year proposal for my small team at Automattic (the parent company of the open source DIY e-commerce platform known as WooCommerce ) -- that we would integrate hardware into our apps and systems so our online merchants could expand into in-person payments. That same year my team and I launched a shipping labels printer integration with EasyPost and the United States Postal Service (USPS) optimized for the USB based <a href="https://www.dymo.com/label-makers-printers/labelwriter-label-printers/dymo-labelwriter-4xl-shipping-label-printer-prints-4-x-6-extra-wide-shipping-labels/SAP_1755120.html">Dymo LabelWriter 4XL</a>. Now I am happy to announce another piece of hardware...</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Today we launch <a href="https://docs.woocommerce.com/document/getting-started-with-in-person-payments-with-woocommerce-payments/">In-Person Payments for WooCommerce Payments</a> - allowing our merchant to get started with in-person card payments with an affordable, simple, super portable Bluetooth card reader backed by <a href="https://stripe.com/">Stripe</a> :) It looks like this:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1840,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://allendotblog.files.wordpress.com/2021/10/woo_in_person_payments_system.jpg?w=1024" alt="" class="wp-image-1840" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I pivoted from an engineering manager and team lead to an engineer again to focus on the technical challenges of integrating the Bluetooth readers and Stripe’s Terminal SDK with iPhones and iPads using Swift. My team and I have been working closely with Stripe engineering on this all year long and today I am happy to say we are opening it up this week to any merchant in the US.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We’ve started with Stripe’s <a href="https://www.bbpos.com/chipper-2x-bt/">BBPOS Chipper 2X BT Bluetooth card reader</a>. It’s a very small headless reader with surprisingly long battery life. It has a dual Classic Bluetooth and Bluetooth LE radio, but relies on BLE to get its work done. It supports chip, swipe and NFC (tap) payments.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Our challenges included integrating reader discovery, connecting, multiple reader management, providing Over the Air (OTA) software updates to the reader, displaying messages in our app from the reader (again, it’s headless) and integrating all that over the Internet to Stripe, our backend and our merchants’ backends (we don’t have a single cloud backend - we don’t control much of the backend - legendary mode enabled!)</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1841,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://allendotblog.files.wordpress.com/2021/10/scanning_for_reader.png?w=1024" alt="" class="wp-image-1841" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://stripe.com/docs/terminal">Stripe’s Terminal SDK</a> is delivered via CocoaPods and, especially with the SDK 2 release, provides for a fairly straightforward integration with our Swift codebase. The biggest challenge in that regard is <a href="https://github.com/woocommerce/woocommerce-ios/blob/develop/docs/architecture-overview.md#main-concepts">our modified Flux architecture</a>: our stores are stateless, with the lion share of actions being triggered by the views and their viewmodels to fetch models from the backend on demand as the user navigates from page to page.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1842,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://allendotblog.files.wordpress.com/2021/10/manage_card_reader.png?w=1024" alt="" class="wp-image-1842" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Hardware makes this more interesting as the readers can disconnect any time they want, demand software updates, need to ask the UI to display messages or switch to other users. It’s kinda like having two users at once:</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/watch?v=kl6rsi7BEtk","type":"video","providerNameSlug":"youtube","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/watch?v=kl6rsi7BEtk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>We ended up having the card reader store hold a reference to a card reader service that does maintain state. It also means that service is the one in the drivers’ seat. User actions are basically limited to initiating or, when the service allows, cancelling payment collection. The service doesn’t dispatch any actions at all. It sets the state to what it wants. We’ll see if changes will be needed, but so far it has held up.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We’re also recommending a capable (although expensive) battery powered portable receipt printer from Brother - the <a href="https://brothermobilesolutions.com/products/mobile-printers/ruggedjet-series/ruggedjet-4-series/brother-ruggedjet-rj4250wbl/">Brother RJ-4250WB-L</a> - it was surprising how few battery powered WiFi Direct printers are on the market. We’re supporting WiFi and WiFi direct for now, but this printer also supports Bluetooth connections and has an SDK for them, so integrating finer control of this versatile printer is an option for us. It was a pleasure working with Brother engineering with this printer selection as well.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1844,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://allendotblog.files.wordpress.com/2021/10/printed_receipt.jpg?w=768" alt="" class="wp-image-1844" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Here’s what capturing a payment looks like, start to finish:</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/watch?v=PQnyKtQVRLg","type":"video","providerNameSlug":"youtube","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/watch?v=PQnyKtQVRLg
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>Net net: I’m delighted to be able to continue to work with hardware and build with Swift again at what is almost exclusively a software company. I’ll share some more in the upcoming weeks on some of the considerations and obstacles we had to overcome to integrate this into our iOS app, our operations and the backends.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I can happily say that working with Stripe on this made it easier. Their <a href="https://stripe.com/docs/terminal">documentation is superb</a> and their engineering support is outstanding. We had to also work out a few things with Apple (to avoid the merchant’s iPhone attempting to pay for the purchase if the reader was too close to an iPhone with Apple Wallet set up) and that went fairly smoothly too (if slower).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>If you’re interested in accepting in-person credit card, debit card and digital wallets with a backend you largely host and manage yourself, take a peek here: <a href="https://docs.woocommerce.com/document/getting-started-with-in-person-payments-with-woocommerce-payments/">https://docs.woocommerce.com/document/getting-started-with-in-person-payments-with-woocommerce-payments/</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>If you’re interested in seeing the Swift code and work involved in integrating with <a href="https://stripe.com/docs/terminal/sdk/ios">Stripe Terminal’s SDK</a> and Bluetooth card readers like the Chipper, you can see my contributions and the rest of the team’s work here: <a href="https://github.com/woocommerce/woocommerce-ios">https://github.com/woocommerce/woocommerce-ios</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>And... if you’re looking, we’re fully remote (another challenge for hardware work) and hiring <a href="https://automattic.com/work-with-us/">https://automattic.com/work-with-us/</a>! We have open positions for senior engineers on both our iOS and Android e-commerce apps <a href="https://automattic.com/work-with-us/job/senior-mobile-engineers-woocommerce-android-ios/">https://automattic.com/work-with-us/job/senior-mobile-engineers-woocommerce-android-ios/</a></p>
<!-- /wp:paragraph -->
