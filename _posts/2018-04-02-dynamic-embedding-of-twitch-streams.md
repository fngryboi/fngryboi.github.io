---
title: Dynamic embedding of Twitch streams
layout: post
categories:
published: true
---

Do you have a website where you want to embed a Twitch.tv stream, but *only* show it when the channel is live and hide it otherwise?

I had the same problem so I decided to throw together a quick script to solve this problem, which I've made available on a [Github Gist](https://gist.github.com/momeenme/f5323765e3358ae27d4a97eb2d63aa3c) for anyone to use, which you can see below.

```
<html>
<head>
  <style>
    .hide { display:none; }

    /* Optional: The following css just makes sure the twitch video stays responsive */
    #twitch {
      position: relative;
      padding-bottom: 56.25%; /* 16:9 */
      padding-top: 25px;
      height: 0;
    }
    #twitch object, #twitch iframe {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }
    </style>
</head>

<body>

  <script src= "https://player.twitch.tv/js/embed/v1.js"></script>

  <div id="twitch" class="hide">
  </div>

  <script type="text/javascript">
    var player = new Twitch.Player("twitch", options);
    var options = {
      channel: "USERNAME", // TODO: Change this to the streams username you want to embed
      width: 640,
      height: 360,
    };

    player.addEventListener(Twitch.Player.READY, initiate)

    function initiate() {
      player.addEventListener(Twitch.Player.ONLINE, handleOnline);
      player.addEventListener(Twitch.Player.OFFLINE, handleOffline);
      player.removeEventListener(Twitch.Player.READY, initiate);
    }

    function handleOnline() {
      document.getElementById("twitch").classList.remove('hide');
      player.removeEventListener(Twitch.Player.ONLINE, handleOnline);
      player.addEventListener(Twitch.Player.OFFLINE, handleOffline);
      player.setMuted(false);
    }

    function handleOffline() {
      document.getElementById("twitch").classList.add('hide');
      player.removeEventListener(Twitch.Player.OFFLINE, handleOffline);
      player.addEventListener(Twitch.Player.ONLINE, handleOnline);
      player.setMuted(true);
    }
  </script>

</body>
</html>
```

[Github Gist of the above code found here](https://gist.github.com/momeenme/f5323765e3358ae27d4a97eb2d63aa3c)

Also if you want to have more stuff that shows up only when the stream is live, then you could encapsulate the twitch div with a parent div like this (don't forget to move the hiding class to the parent):

{% highlight html %}
<div id="parent" class="hide"> <!-- named parent for demonstration purposes, you can name it whatever you want -->

<!-- Here you can place anything you want to show above the embedded stream -->

<div id="twitch">
</div>

<!-- Here you can place anything you want to show underneath the embedded stream -->

</div>

{% endhighlight %}

But to make this work you need to change the javascript bit so it targets the parent div and not the twitch div, like this:

{% highlight javascript %}

var player = new Twitch.Player("twitch", options);
var options = {
  channel: "USERNAME", // TODO: Change this...
  width: 640,
  height: 360,
};

player.addEventListener(Twitch.Player.READY, initiate)

function initiate() {
  player.addEventListener(Twitch.Player.ONLINE, handleOnline);
  player.addEventListener(Twitch.Player.OFFLINE, handleOffline);
  player.removeEventListener(Twitch.Player.READY, initiate);
}

function handleOnline() {
  document.getElementById("parent").classList.remove('hide'); // *****
  player.removeEventListener(Twitch.Player.ONLINE, handleOnline);
  player.addEventListener(Twitch.Player.OFFLINE, handleOffline);
  player.setMuted(false);
}

function handleOffline() {
  document.getElementById("parent").classList.add('hide'); // *****
  player.removeEventListener(Twitch.Player.OFFLINE, handleOffline);
  player.addEventListener(Twitch.Player.ONLINE, handleOnline);
  player.setMuted(true);
}

{% endhighlight %}

Note: I've highlighted all the changes that were made from the old "twitch" div to the new "parent" div with `// *****`.

That's all you really need to get started. However, if you have some web design skills you can really take this to the next level.

Good luck!