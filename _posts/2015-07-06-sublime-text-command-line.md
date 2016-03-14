---
layout: post
title: Open Files in Sublime Text 3 from the Command Line
description:
comments: true
post_author: Anthony Ramella
categories: productivity tools
---

Sublime Text 3 comes with a command line tool called <code>subl</code> which can be used to open files in Sublime Text. However, you first have to do some configurations in order to enable this tool. If you are a heavy command line user, this tool is an absolute life saver.

### Setting up the load $PATH
The first step is to create a [symlink](https://en.wikipedia.org/wiki/Symbolic_link) that will allow you to run <code>subl</code> from the command line. In the documentation on this tool, it is assumed you have <code>~/bin</code> (or <code>/Users/username/</code>) in your load path, which <i>would</i> be located in <code>/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl</code>. However, since the <code>/usr/local/bin</code> is already in your load path by default on OS X, it serves as a better place to assign the <code>subl</code> symlink.

To check your load $PATH, you want to run <code>echo $PATH</code> in the terminal.

Your results might vary slightly but it will most likely return <code>/usr/local/bin</code> at the end of the line, which is included by default on OS X.

### Installation
The first and only step to the installation is to simply run this line in your terminal:
 <code>ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime</code>

As a side note, I prefer to name the symlink "<code>sublime</code>" instead of "<code>subl</code>" just to be more specific. Plus, terminal symlinks can be auto-completed by pressing tab once the initial bit of the command has been typed. If the extra keystroke is a bit much for you, feel free to change the line above to the "<code>subl</code>" symlink at the end of <code>/usr/local/bin/</code>.

### Launching

In your terminal, go to your Documents directory by running:

<code>cd ~/Documents</code>

Next, to test that the symlink is working, open the contents of your Documents folder in Sublime Text. So this will simply be the symlink followed by the file name you want to open, in this case we are opening all contents of the Documents folder.

<code>sublime .</code>

### Conclusion
This is a really handy tool to have as a heavy user of the command line. It allows you to remain in the command line while opening directories or files without having to launch your Finder to search around. It is also very useful when opening hidden files in Sublime Text. I found myself using it more frequently than I imagined and I hope it helps your workflow like it has mine.
