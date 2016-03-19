---
layout: post
title: Open Files in Sublime Text 3 from the Command Line
description:
comments: true
post_author: Anthony Ramella
categories: productivity tools
---

Sublime Text 3 comes with a command line tool called <pre>subl</pre> which can be used to open files in Sublime Text. However, you first have to do some configurations in order to enable this tool. If you are a heavy command line user, this tool is an absolute life saver.

### Setting up the load $PATH
The first step is to create a [symlink](https://en.wikipedia.org/wiki/Symbolic_link) that will allow you to run <pre>subl</pre> from the command line. In the documentation on this tool, it is assumed you have <pre>~/bin</pre> (or <pre>/Users/username/</pre>) in your load path, which <i>would</i> be located in <pre>/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl</pre>. However, since the <pre>/usr/local/bin</pre> is already in your load path by default on OS X, it serves as a better place to assign the <pre>subl</pre> symlink.

To check your load $PATH, you want to run <pre>echo $PATH</pre> in the terminal.

Your results might vary slightly but it will most likely return <pre>/usr/local/bin</pre> at the end of the line, which is included by default on OS X.

### Installation
The first and only step to the installation is to simply run this line in your terminal:
 <pre>ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime</pre>

As a side note, I prefer to name the symlink "<pre>sublime</pre>" instead of "<pre>subl</pre>" just to be more specific. Plus, terminal symlinks can be auto-completed by pressing tab once the initial bit of the command has been typed. If the extra keystroke is a bit much for you, feel free to change the line above to the "<pre>subl</pre>" symlink at the end of <pre>/usr/local/bin/</pre>.

### Launching

In your terminal, go to your Documents directory by running:

<pre>cd ~/Documents</pre>

Next, to test that the symlink is working, open the contents of your Documents folder in Sublime Text. So this will simply be the symlink followed by the file name you want to open, in this case we are opening all contents of the Documents folder.

<pre>sublime .</pre>

### Conclusion
This is a really handy tool to have as a heavy user of the command line. It allows you to remain in the command line while opening directories or files without having to launch your Finder to search around. It is also very useful when opening hidden files in Sublime Text. I found myself using it more frequently than I imagined and I hope it helps your workflow like it has mine.
