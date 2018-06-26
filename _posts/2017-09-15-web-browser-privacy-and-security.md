---
layout: post
title: Know Thy Browser - A Study on Web Browser Security & Privacy
date: 2017-09-15 00:18:23
author: Anthony Ramella
categories: security privacy
image_preview:
description: A brief rundown of the privacy and security of popular third-party browsers. Some solutions are offered and many links are provided.
comments: true
---

## [Chrome](https://www.google.com/chrome/index.html)

SECURITY: Google Chrome is a freeware browser based on the open-source [Chromium project](http://www.chromium.org/Home). Some proprietary components have been added to optimize features such as upgrading, crash reports, a PDF viewer, media codec support and a randomly generated token that sends basic installation data back to Google. Although Chrome itself is not open-sourced, a nice feature is that Google does offer a very lucrative [bounty program](https://www.google.com/about/appsecurity/chrome-rewards/) for reporting vulnerabilities along with its own Project Zero. Recently, Google has made it so that Chrome now quietly [installs a mandatory DRM module](https://boingboing.net/2017/01/30/google-quietly-makes-optiona.html) without an option to disable it. This makes it difficult and dangerous for security researchers to investigate the possibility of vulnerabilities in Chrome [[more information]](https://bugs.chromium.org/p/chromium/issues/detail?id=686430). 

PRIVACY: While Chrome offers some decent security features aside from the numeous plugins that should be added to enhance its security, it also has perhaps the worst reputation among popular web browsers in terms of privacy. Chrome comes installed with an RLZ identifier which sends an encoded string to Google used to measure promotional campaigns. This cannot be turned off as a setting, but Google kindly will provide the source code so you can decode it yourself! Also there is no word from Google whether RLZ can be disabled on mobile Chrome. The Chrome developers have also turned off the "Do Not Track" option which can and should be manually [turned on](https://support.google.com/chrome/answer/2790761) so your browsing data isn't collected. According to Chrome's privacy policy can be found [here](https://www.google.com/chrome/browser/privacy/index.html).

NOTE: If you must use Chrome as your primary browser, I would highly recommend creating separate profiles for certain browsing activity. One for browsing trusted sites, another for mostly trusted sites (with [these](https://www.superantispyware.com/blog/2017/05/10/our-top-5-google-chrome-extension-picks-for-better-web-security/) security enhancment extensions installed) and a third with JavaScript and cookies disabled for browsing untrusted sites.


## [Firefox](https://www.mozilla.org/en-US/firefox/new/)

SECURITY: Firefox lets you create different user profiles called [containers](https://testpilot.firefox.com/experiments/containers) which can be used in the same way as the previously suggested Chrome profiles. Since Firefox switched to HTTPS support, any login that doesn't support HTTPS displays prompt in the password field reminding the user that their login could be compromised. On top of being free and open-sourced, Mozilla also offers a [bug bounty](https://www.mozilla.org/en-US/security/bug-bounty/) reward for Firefox. 

PRIVACY: Mozilla makes it very clear that they put a high priority on privacy. On top of being completely open source, Mozilla will not sell browsing data to other companies since they are a non-profit. Firefox uses [tracking protection](https://developer.mozilla.org/en-US/Firefox/Privacy/Tracking_Protection) during private sessions but it can be enabled on the default profile as well. Unfortunately, some previous versions of Firefox used a legacy web extension that offered a lot of freedom for developers at the expense of being quite invasive by introducing several vulnerabilities which are covered in [this paper](https://www.exploit-db.com/docs/24541.pdf). Considering Firefox has limited protection out of the box compared to a browser like Brave or Tor, there are some addons that can greatly improve the browser's security. It is recommended to use [TheCreeper/PrivacyFox](https://github.com/TheCreeper/PrivacyFox) to enhance privacy settings for Firefox.

Read Mozilla's privacy policy [here](https://www.mozilla.org/en-US/privacy/firefox/).


## [Brave](https://www.brave.com/download/)

SECURITY: Brave is a browser founded by Brendan Eich, co-founder of the Mozilla Project and creator of JavaScript. Brave currently does not support addons or plugins, but it offers plenty of attractive built-in features. It comes with encrypted communication out of the box via [HTTPS Everywhere](https://www.eff.org/https-everywhere), which needs to be downloaded separately as an add-on for other browsers. Some other great default security features are password manager support, ad-blocking, tracker blocking and anti-phishing protection.

PRIVACY: Braves makes the list of 3 browsers recommended by [privacytools.io](https://www.privacytools.io/#browser), which makes it worth a serious look. A notable feature that Brave has is [WebTorrent integration](https://torrentfreak.com/brave-a-privacy-focused-browser-with-built-in-torrent-streaming-170219/) for built in streaming. Brave makes W3C [DRM](https://en.wikipedia.org/wiki/Digital_rights_management) optional by allowing users to [disable it](https://news.ycombinator.com/item?id=13519006) and even gives a warning about using it. Besides free ad-blocking, what really sets Brave apart from other browsers is that it allows users to collect micro-donations called [Brave Payments](https://brave.com/faq/#brave-payments), rewarding users with [Basic Attention Token](https://basicattentiontoken.org/) (BAT).

"BAT will allow publishers, advertisers, and users to connect in an online environment that reduces fraud, privacy violations and “malvertisements” while increasing publisher revenue.[1](https://www.cryptocoinsnews.com/brave-announces-blockchain-digital-advertising-platform-with-ethereum-based-token-rewards-for-users/)" BAT offers an anonymous and private p2p ad-tech solution for collecting rich user metrics by eliminating 3rd party intermediaries and rewarding all who participate.


## [Tor Browser](https://www.torproject.org/projects/torbrowser.html)

TOR (short for The Onion Router) really deserves it's own writeup, but here's the quick rundown. Tor Browser is the flagship application of The Tor Project and as far as browsing goes, it is the undisputed king when it comes to privacy, security and anonymity. It uses a tech developed by U.S. Naval Research Labratory employees in the 90's called "onion routing", which implements encrypted nested application layers over the user's network connection.

SECURITY: As stated on the Tor Project website, "[Tor] protects you by bouncing your communications around a distributed network of relays run by volunteers all around the world". Tor is so secure that the FBI could not even locate or de-anonymize the Tor user who hacked into the Hillary Clinton email server. Ultimately, any vulnerabilities come down to how browser is configured and used. A good start would be referring to [Tor's documentation](https://www.torproject.org/docs/documentation.html.en) on installing and configuring Tor for optimal security.

PRIVACY: Once again, Tor Browser is the king when it comes to privacy browsers and anonymity and even [the NSA agrees](https://www.theguardian.com/world/2013/oct/04/nsa-gchq-attack-tor-network-encryption). However, it's not a perfect solution. [Naked Security points out](https://nakedsecurity.sophos.com/2015/06/25/can-you-trust-tors-exit-nodes/) that Tor had been mistakenly used as an end-to-end encryption tool, which is certainly is not. Basically, no matter how many nodes are relayed together, traffic must eventually escape the network through exit nodes. Years before Snowden, a Sweedish computer consultant named Dan Egerstad was able to leak hundreds of confidential government emails by using a packet sniffer aimed at POP3 and IMAP traffic coming through [Tor exit nodes](http://www.zdnet.com/article/sensitive-government-e-mails-leak-through-tor-exit-nodes/).
