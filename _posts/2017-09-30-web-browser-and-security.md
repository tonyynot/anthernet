---
layout: post
title: Web Browser Privacy and Security Rundown - Google Chrome
date: 2017-09-15 00:18:23
author: Anthony Ramella
categories: security
image_preview:
description: 
---


## Chrome

**Security:** Google Chrome is a freeware browser based on the open-source [Chromium project](http://www.chromium.org/Home). Some proprietary components have been added to optimize features such as upgrading, crash reports, a PDF viewer, media codec support and a randomly generated token that sends basic installation data back to Google. While Chrome itself is not open-sourced, a nice feature is that Google does offer a very lucrative [bounty program](https://www.google.com/about/appsecurity/chrome-rewards/) for reporting vulnerabilities along with its own Project Zero. Recently, Google has made it so that Chrome now quietly [installs a mandatory DRM module](https://boingboing.net/2017/01/30/google-quietly-makes-optiona.html) without an option to disable it. This makes it difficult and dangerous for security researchers to investigate the possibility of vulnerabilities in Chrome [[More information]](https://bugs.chromium.org/p/chromium/issues/detail?id=686430). 

**Privacy:** While Chrome offers some decent security features aside from the numeous plugins that should be added to enhance its security, it also has perhaps the worst reputation among popular web browsers in terms of privacy. Chrome comes installed with an RLZ identifier which sends an encoded string to Google used to measure promotional campaigns. This cannot be turned off as a setting, but Google kindly will provide the source code so you can decode it yourself! Also there is no word from Google whether RLZ can be disabled on mobile Chrome. The Chrome developers have also turned off the "Do Not Track" option which can and should be manually [turned on](https://support.google.com/chrome/answer/2790761) so your browsing data isn't collected. According to Chrome's privacy policy can be found [here](https://www.google.com/chrome/browser/privacy/index.html).

**Note:** If you must use Chrome as your primary browser, I would highly recommend creating separate profiles for certain browsing activity. One for browsing trusted sites, another for mostly trusted sites (with [these](https://www.superantispyware.com/blog/2017/05/10/our-top-5-google-chrome-extension-picks-for-better-web-security/) security enhancment extensions installed) and a third with JavaScript and cookies disabled for browsing untrusted sites.

## Firefox

**Security:** Firefox lets you create different user profiles called [containers](https://testpilot.firefox.com/experiments/containers) which can be used in the same way as the previously suggested Chrome profiles. Since Firefox switched to HTTPS support, any login that doesn't support HTTPS displays prompt in the password field reminding the user that their login could be compromised. On top of being free and open-sourced, Mozilla also offers a [bug bounty](https://www.mozilla.org/en-US/security/bug-bounty/) reward for Firefox. 

**Privacy:** Mozilla makes it very clear that they put a high priority on privacy. On top of being completely open source, Mozilla will not sell browsing data to other companies since they are a non-profit. Firefox uses [tracking protection](https://developer.mozilla.org/en-US/Firefox/Privacy/Tracking_Protection) during private sessions but it can be enabled on the default profile as well. Unfortunately, some previous versions of Firefox used a legacy web extension that offered a lot of freedom for developers at the expense of being quite invasive by introducing several vulnerabilities which are covered in [this paper](https://www.exploit-db.com/docs/24541.pdf). While Firefox has limited protection out of the box compared to a browser like Brave or Tor, there are some addons that can greatly improve the browser's security. It is recommended to use [TheCreeper/PrivacyFox](https://github.com/TheCreeper/PrivacyFox) to enhance privacy settings for Firefox.

Read Mozilla's privacy policy [here](https://www.mozilla.org/en-US/privacy/firefox/).

## Brave

**Security:** Brave is a browser founded by Brendan Eich, co-founder of the Mozilla Project and creator of JavaScript. It comes with encrypted communication out of the box via [HTTPS Everywhere](https://www.eff.org/https-everywhere), which needs to be downloaded separately as an add-on for other browsers. Some other great default security features are password manager support, ad-blocking, tracker blocking and anti-phishing protection. Brave does not support plugins or addons, although because of its impressive features out of the box, there isn't much need for 3rd party extensions.

**Privacy** A unique feature that Brave offers is [WebTorrent integration](https://torrentfreak.com/brave-a-privacy-focused-browser-with-built-in-torrent-streaming-170219/) for built in streaming. Brave makes W3C [DRM](https://en.wikipedia.org/wiki/Digital_rights_management) optional by allowing users to [disable it](https://news.ycombinator.com/item?id=13519006) and even gives a warning about using it. While ads and tracking are disabled for Brave, the browser does reward users with an Ethereum based digital currency called Basic Attention Tokens (BAT). "BAT will allow publishers, advertisers, and users to connect in an online environment that reduces fraud, privacy violations and “malvertisements” while increasing publisher revenue."[1](https://www.cryptocoinsnews.com/brave-announces-blockchain-digital-advertising-platform-with-ethereum-based-token-rewards-for-users/). Most noteworthy of all, Brave is the recommended browser of [Privacytools.io](https://www.privacytools.io/#browser).