---
layout: post
title: How I Designed and Coded This Blog
description: Using Jekyll, Bourbon, Gulp and a lot of free time, I redesigned my blog in just a weekend.
comments: true
tags: design code jekyll gulp tutorials
---
### Setting up Jekyll and Gulp
It has been well over a year that I've been using Jekyll as a static site generator for my blog and up until now, I've been downloading and modifying various themes. I decided to start with a fresh base install of Jekyll and roll my own theme using Sass to process my CSS.

I wanted to use a task runner for my build, specifically Gulp.js to handle my Sass compiling and BrowserSync to auto refresh my changes on each save. I came across [this](https://github.com/shakyShane/jekyll-gulp-sass-browser-sync) Github repo which provided an excellent gulpfile with the default Jekyll build files. In order to get my build system up and running, I ran the following installations:

Jekyll - <code>$ gem install jekyll</code><br>
NodeJS - use the installer found [here](https://nodejs.org/en/).<br>
GulpJS - <code>$ npm install -g gulp</code> (mac users should use <code>sudo</code>)

I did have to run <code>sudo npm install</code> for each of the dependencies listed in the gulpfile. Once that was done, running a simple <code>gulp</code> command got my Jekyll build up and running with BrowserSync and Sass compiling.


### Installing Bourbon and Neat
Now that I had my build system up and running, I started thinking about design and layout. All I knew was I wanted to keep both the design and code minimal. This meant no Bootstrap or Foundation. I remembered trying to use [Bourbon](http://bourbon.io) and the [Neat](http://neat.bourbon.io/) grid a while back but not understanding enough about the grid system and Sass to be able to properly implement it into my project. So I revisted Bourbon and Neat this time and was surprised with how quick and easy it is to use. 

Installation is as simple as running a gem install:<br>
<code>$ gem install bourbon</code><br>
Then loading Bourbon into the project with<br> 
<code>$ bourbon install</code>

*Note: Installing Neat is exactly the same*<br>
<pre>
$ gem install neat 
$ neat install
</pre>

Inside my <code>_scss</code> folder, I created a file to store my mixins and another file to store my color and font variables. Inside my <code>_main.scss</code>, the Bourbon and Neat .scss files are included along with <code>_variables.scss</code> and <code>_mixins.scss</code> at the top of the stylesheet as such:
<pre>
@import "bourbon/bourbon";
@import "neat/neat";
@import "variables";
@import "mixins";
</pre>

### Design & Layout
With everything setup in just a few minutes, I was able to start designing with ease. Having my Gulp build system running BrowserSync, trying out new fonts, colors and grid layouts with Neat was a breeze. It actually made the design part of the build very fun for me and trying out new ideas was a lot less tedious. Using the Neat grid changed the way I approach CSS. Things like nesting pseudo elements, using variables and defining breakpoints and media queries within a class seems to be the most logical way to write CSS. 

Avoiding tons of nested divs with long lists of classes such as <code>small-12 medium-10 large-6 columns</code> kept my markup semantic and clean. The Neat grid makes it as simple as using <code>@include span-columns(12);</code> inside the class itself. For media breakpoints, just throw in <code>@media screen and (max-width: 887px){...}</code>.

### Theming Made Easy with Sass
When I was downloading and modifying other Jekyll themes, I found that the things I wanted to change most were font and color variations. With that in mind, I designed this theme so that the colors and fonts could easily be changed without having to replace every instance of that color/font in the document. I did this by making variables targeting each element that could be modified. 

For example, lets say I defined the <code>$red</code> variable in my <code>_variables.scss</code> as <code>#FF0000</code>. At the top of my <code>_main.scss</code>, I can assign the <code>$red</code> variable to <code>$base_font</code> so in order to change the base font color, just assign any color variable defined in <code>_variables.scss</code> to <code>$base_font</code>. This will change the color in any class that has <code>$base_font</code> set as its color instead of having to do a find/replace all.

That's all there is to it! If you have any questions or comments, feel free to [tweet](http://www.twitter.com/tonecodes) at me or comment below.
