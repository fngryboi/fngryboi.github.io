---
title: Twitch Stream Embed-When-Live
layout: post
categories:
  - blog
published: true
---

> TL;DR: I rewrote a script to embed and tuck away a twitch stream depending on if the channel is online/offline. You can find it here: [TwitchCleverEmbed](https://github.com/fngryboi/TwitchCleverEmbed) or [Download .ZIP](https://github.com/fngryboi/TwitchCleverEmbed/archive/master.zip)

### Introduction

I decided to pick up an old github repository that used to host a method for embedding and tucking away a twitch stream depending on whether the channel was streaming or not. It didn't work anymore because since then Twitch had updated their API and I had moved on to do other things, and just didn't get around to it.

But I finally found a reason to pick it because I had been thinking about starting to stream my game development extravaganza on Twitch this summer, and could use it right here. So I decided to take a look at [Twitch's new API](https://dev.twitch.tv/docs) and see how it worked. And with the new API my script became more efficient, firstly because I've become better at programming since I enrolled at the university programme about game development and secondly because I found that the new API had events listeners I could utilize.

### The old way

The old version, which was called TwitchLiveEmbed had the problem that it was checking the Twitch channels stream through the API to see if it was live with a certain interval running on the client side. Which posed several problems:
1. If the user changed the interval to something too low, it could be too fast causing the API key used to be blocked as the server received way too many requests. Which, if the user didn't change the key from the repository, was created on my account and therefore holding me accountable...
2. If the user changed the interval to an interval too high, the end-user might miss the first part of the stream and then once the stream ended the twitch player might hang around with "Offline" written on it for too long.
3. The end-user could see the twitch player pop up really promptly as he just entered the website, as it wasn't hidden by default but instead became hidden after the script had run (which it might not do if the end-user had javascipt disabled).

### The new way

The *new version* however has improved a lot compared to the older version

Scripts always run a bit late and because we need to load in a Twitch Player before we check if the channel is online or offline I made it hidden by default, by adding a div class called `hide` which just has the following CSS parameters `display:none;` to it. Meaning we hide everything inside the div `twitch`. Our script will then later remove or add the class `hide` depending on if the channel goes online or offline.

*Note: If the end-user has javascript disabled this script wouldn't run at all, therefore it wouldn't even generate an embedded twitch player.*

The script works like this:
1. Create a player reference based on the USERNAME and other information stored in a function called options, then target a div element where it creates an embedded player and the player gets muted in case ads starts playing.
2. Runs the initiate function, which creates two event listeners that run two separate functions, one for online and one for offline.

The player reference and options looks like this:
```
var player = new Twitch.Player("twitch", options);
var options = {
  channel: "USERNAME",
  width: 640,
  height: 360,
};
```
The online function looks like this:

```
function handleOnline() {        
  document.getElementById("twitch").classList.remove('hide');
  player.removeEventListener(Twitch.Player.ONLINE, handleOnline);
  player.addEventListener(Twitch.Player.OFFLINE, handleOffline);

  player.setMuted(false);
}
```
The offline function looks like this:
```
function handleOffline() {
  document.getElementById("twitch").classList.add('hide');
  player.removeEventListener(Twitch.Player.OFFLINE, handleOffline);
  player.addEventListener(Twitch.Player.ONLINE, handleOnline);

  player.setMuted(true);
}
```

If the event listener for online gets triggered, it will run the `handleOnline` function which will remove the event listener that checks if the player goes online as we don't need it anymore. And remove the div class `hide` from the div element `twitch` to make the twitch player visible. It also unmutes the player so you can hear the stream.

If the event listener for offline gets triggered, it does the opposite.

Therefore there will always be one event listener running that checks for the opposite state that the stream is in. To dynamically hide and mute or display and unmute the stream.

**You can find the everything you need in the repository over at [TwitchCleverEmbed](https://github.com/fngryboi/TwitchCleverEmbed), if you want to test it just [download it as a .zip](https://github.com/fngryboi/TwitchCleverEmbed/archive/master.zip) and change the username inside `index.html` from mine (fngryboi) into whatever channel is currently live on [Twitch.tv](http://twitch.tv) or your own and do a test stream.**

If you encounter any problems just [open an issue over on the repository](https://github.com/fngryboi/TwitchCleverEmbed/issues) and I'll see what I can do!

### The future

For the future I want to add an optional chat to this, with a boolean that the user can set to true or false depending on if s/he wants the functionality.

I might also add another demo on the github repository for a working example of the optional step 3 from the instructions in the [TwitchCleverEmbed](https://github.com/fngryboi/TwitchCleverEmbed) repository, for if the user wanted to add more stuff to display under or above the stream like for example a link to the donation/tip service or other information that could be from the Twitch Panels under the stream.
