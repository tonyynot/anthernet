---
layout: post
title: Create an Awesome .bash_profile for Your Mac Terminal
description: Hacking the hidden Mac file known as the 'dot file' or .bash_profile, which can be coded to customize your command line settings by using aliases.
comments: true
author: Anthony Ramella
tags: code productivity
---

## What is a .bash_profile and Why Should I Care?
Hidden inside your Mac's user directory is a file called .bash\_profile. Your .bash\_profile contains all the configurations and preferences for your command line and assigns it a user specific environment. First off, why would you want to edit your terminal profile? If you're a heavy terminal user, you may find it useful to customize certain text colors, change command line prompts, edit your $PATH directory and add aliases to certain commonly used functions.

## Editing your .bash_profile

* Open your Terminal app<br>
* Type <code>cd ~/</code> to navigate to your home folder.<br>
* Type <code>touch .bash\_profile</code> to create your dot file if you don't have one already. <br>
* You can edit .bash\_profile in TextEdit by typing <code>open -e .bash\_profile</code> or if you use Sublime Text, you can open the file using the super handy [Sublime Text OSX Command Line tool](https://www.sublimetext.com/docs/2/osx_command_line.html) by typing <code>subl .bash_profile</code>.<br>
* Last, type <code>. .bash\_profile</code> to reload .bash_profile and update any aliases you just added.

## Your awesome new .bash\_profile
The following is a compiled .bash_profile that I came across on GitHub and forked it for future reference. It's a very concise and well commented document that has a ton of useful aliases. [Here](https://gist.github.com/natelandau/10654137) is the link to the file via GitHub Gist thanks to [Nathaniel Landau](https://github.com/natelandau) who compiled the file.

{% gist natelandau/10654137 %}