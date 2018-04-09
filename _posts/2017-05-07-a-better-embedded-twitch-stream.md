---
title: Twitch.tv - Embed stream only when it's live
layout: post
categories:
  - streaming
  - scripts
published: true
---

Do you have a website where you want to embed a Twitch stream (maybe your own channels stream), but only show it when the channel is actually live?

I had the same problem so I decided to throw together a quick script to solve this problem which you can see below.

<script src="https://gist.github.com/fngryboi/f5323765e3358ae27d4a97eb2d63aa3c.js"></script>

Also if you want to have more stuff that shows up only when the stream is live, then you could encapsulate the twitch div with a parent div like this (don't forget to move the hiding class to the parent):

´´´
<div id="parent" class="hide"> <!-- named parent for demonstration purposes, you can name it whatever you want -->

<!-- Here you can place anything you want to show above the embedded stream -->

<div id="twitch">
</div>

<!-- Here you can place anything you want to show underneath the embedded stream -->

</div>

´´´

But to make this work you need to change the javascript bit so it targets the parent div and not the twitch div, like this:

´´´

var player = new Twitch.Player("twitch", options); // ***** Changed from "twitch" to "parent"
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
  document.getElementById("parent").classList.remove('hide'); // ***** Changed from "twitch" to "parent"
  player.removeEventListener(Twitch.Player.ONLINE, handleOnline);
  player.addEventListener(Twitch.Player.OFFLINE, handleOffline);
  player.setMuted(false);
}

function handleOffline() {
  document.getElementById("parent").classList.add('hide'); // ***** Changed from "twitch" to "parent"
  player.removeEventListener(Twitch.Player.OFFLINE, handleOffline);
  player.addEventListener(Twitch.Player.ONLINE, handleOnline);
  player.setMuted(true);
}

´´´

Note: I've highlighted all the changes that were made with ´// ***** Changed from "twitch" to "parent"´.

That's all you really need to get started. However, if you have some web design skills you can really take this to the next level.
