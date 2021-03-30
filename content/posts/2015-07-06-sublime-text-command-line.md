---
layout: post
title: Open Files in Sublime Text 3 from the Command Line
description:
comments: true
post_author: Anthony Ramella
tags: productivity tools
---

Sublime Text 3 comes with a command line tool called ``subl`` which can be used to open files in Sublime Text. However, you first have to do some configurations in order to enable this tool. If you are a heavy command line user, this tool is an absolute life saver.

## Setting up the load $PATH
The first step is to create a [symlink](https://en.wikipedia.org/wiki/Symbolic_link) that will allow you to run ``subl`` from the command line. In the documentation on this tool, it is assumed you have ``~/bin`` (or ``/Users/username/``) in your load path, which <i>would</i> be located in 
``/Applications/Sublime Text.app Contents/SharedSupport/bin/subl``. However, since the ``/usr/local/bin`` is already in your load path by default on OS X, it serves as a better place to assign the ``subl`` symlink.

To check your load $PATH, you want to run ``echo $PATH`` in the terminal.

Your results might vary slightly but it will most likely return ``/usr/local/bin`` at the end of the line, which is included by default on OS X.

## Installation
The first and only step to the installation is to simply run this line in your terminal:

``ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime``

As a side note, I codefer to name the symlink "``sublime``" instead of "``subl``" just to be more specific. Plus, terminal symlinks can be auto-completed by codessing tab once the initial bit of the command has been typed. If the extra keystroke is a bit much for you, feel free to change the line above to the "``subl``" symlink at the end of ``/usr/local/bin/``.

## Launching

In your terminal, go to your Documents directory by running:

``cd ~/Documents``

Next, to test that the symlink is working, open the contents of your Documents folder in Sublime Text. So this will simply be the symlink followed by the file name you want to open, in this case we are opening all contents of the Documents folder.

``sublime .``

## Conclusion
This is a really handy tool to have as a heavy user of the command line. It allows you to remain in the command line while opening directories or files without having to launch your Finder to search around. It is also very useful when opening hidden files in Sublime Text. I found myself using it more frequently than I imagined and I hope it helps your workflow like it has mine.
