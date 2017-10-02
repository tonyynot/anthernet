---
layout: post
title: Building a Twitter Bot with Node.js
description: Building a Twitter bot can be a fun and easy way to learn programming. Here's how I built one using Node and a large library of images.
comments: true
tags: tutorials, how-to, learning, code, css 
---

So I have a huge unorganized local directory of thousands of images that were scraped from Tumblr and various subreddits. The bot uses Node file system and a sorting module to randomly select an image and post it every hour. It then deletes the photo after it's been posted so there are no duplicates. I should note that this implementation is more of a test run and that I'd like to eventually use the code for some other bots that have a more focused theme.

Here's how it works.

{% highlight javascript %}
var Twit = require('twit')
    fs  = require('fs'),
    path = require('path'),
    shuffle = require('shuffle-array'),
    config = require(path.join(__dirname, 'config.js'));
 {% endhighlight %}
 
It's worth noting that in my dependencies I'm including a config.js file which stores my API keys separately. It will be passed through the tweet variable for authentication.

{% highlight javascript %}
function tweetImage() {
    var tweet = new Twit(config);
    // Define images path
    var imagesArray = fs.readdirSync('./images/');
    // Shuffle images
    shuffle(imagesArray);
    // Pick random image
    var randImage = shuffle.pick(imagesArray);
    console.log("IMAGE CHOSEN: " + randImage);
    // Convert content to base64
    var b64content = fs.readFileSync('./images/' + randImage, {
        encoding: 'base64'
    });
    // Assign b64 content to tweet
    tweet.post('media/upload', {
        media_data: b64content
    },
{% endhighlight %}

The imagesArray variable is assigned to read all contents of the images directory. The array is then shuffled using the shuffle-array package which also selects a random image to which is then encoded to base64.

{% highlight javascript %}
function(err, data, response) {
   if (err) {
      console.log('ERROR');
      console.log(err);
   } 
   else {
      console.log('UPLOADING....');
      // Post tweet
      tweet.post('statuses/update', {
         media_ids: new Array(data.media_id_string)
      },
      function(err, data, response) {
         if (err) {
            console.log('ERROR');
            console.log(err);
         } 
         else {
            console.log('An image has successfully been posted!');
            // Delete image after tweeting
            fs.unlinkSync('./images/' + randImage);
         }
      });
   }
});
{% endhighlight %}

The function that posts the image to Twitter is wrapped in a conditional for basic error handling. Once the image has successfully been posted, the file is deleted through node file system so that it cannot be posted again.

Lastly, the tweetImage function is ran in a 1 hour interval:
{% highlight javascript %}
setInterval(function() {
    tweetImage();
}, 600000 * 6); // Tweets in 1 hour intervals
{% endhighlight %}


## Initial troubleshooting
Since I'm dealing with a local file directory for now, the bot is running locally and is dependent on my machine running (silly, I know). So what I'm working on doing next is uploading my image directory to Google Drive and have the bot run on a server while using Google's Node.js client to determine the path. My first night running the bot, I went to bed and noticed it had stopped running when my computer was inactive (duh). So to fix this issue, I installed [forever](https://github.com/foreverjs/forever) which is a CLI tool that ensures my node server runs continuously.

Here is the link to the repository via [Github](https://github.com/tonyynot/random-image-tweet). A demo of the bot can be found [here](http://twitter.com/blank_waves).
I found I enjoy building Twitter bots and I'd like to improve this concept to the point where it's an account people would actually follow. Thanks for reading!