---
layout: post
title: Theme Overview
categories:
  - blog
published: false
---
This blog post serves to quickly go over what has been put into this blog, more specifically the theme and foundation of this blog, and this post will most likely be updated as more features get implemented as time goes on.

### Features in place on top of Lagom:

1. Adress bar with custom colors that can be configured in the `theme.yml` file
2. [TwitchCleverEmbed](http://github.com/fngryboi/TwitchCleverEmbed) integrated, a script that embeds a Twitch stream when the channel is live and hides it when the channel goes offline.
3. [FitVids.js](http://fluidvidsjs.com) integrated, to make embedded videos from common video hosting sites responsive.
4. Added a Dark theme option in `theme.yml` if you prefer that over the light theme from the original Lagom theme.
5. Added a Youtube social link, where you use your unique ID from `http://youtube.com/channel/<your-channel-ID>` which you can find if you go to www.youtube.com and click on My Channel in the left menu. You should be able to extract your channel ID from the URL from there. You paste your channel ID in the social section of the `theme.yml` file.

### Features that I want to add in the future:

1. Extend TwitchCleverEmbed, not just embed the twitch player but also a chat (which you can toggle on and off), will be added to the official repository as well. But for this theme the variable will be available in the `theme.yml` file.
2. Image Previewing much like how [Medium](http://medium.com) looks. By extracting code from [this repository](https://github.com/rpearce/react-medium-image-zoom).
3. Optional comment platforms that are easy to setup by just typing in your username or unique ID from the `theme.yml` file.
4. Switch out [FluidVids.js](http://fluidvidsjs.com) to [SuperEmbed.js](https://github.com/corbindavenport/superembed.js) as it supports more video providers but also because it removes the need for jQuery. As the theme currently has it integrated but it's just FluidVids.js that actually uses it, so we could save an HTTP request from this but also support more video providers out of the box - as you have to manually add any video providers outside of youtube and vimeo.
5. Add optional [custom text selection color](https://css-tricks.com/overriding-the-default-text-selection-color-with-css/) parameter for the theme, so instead of the standard selection it will use the theme color instead. With a variable for if you want to utilize this or leave it as the standard, as some colors might not be good fit with this. Three variables will be added to `theme.yml` for this, one for if you want to enable it, one for if you want to use a custom color that isn't the theme color and lastly the custom selection color variable.
6. Discord icon (FontAwesome doesn't have one at the moment of writing this), Twitch (FontAwesome has one implemented, but no square version of it is available) and Pinterest social icon (square version exist, just not implemented yet...)
Might redo them all to give social icons a square background and use their standard logo instead on top, as not all icons have a square version available and manually adding a square background might end up being the only alternative...

If you have any ideas or suggestions yourself you can always fork the project and do a pull request when you've implemented the feature, or [open a new issue](https://github.com/fngryboi/lagom-plus/issues) in the repository with your suggestion.

### Setting up your own

You can find the whole theme repository over at [http://github.com/fngryboi/lagom-plus](http://github.com/fngryboi/lagom-plus), where you can fork it into your own Github account and rename it to `<your-github-handle>.github.io` to host it from Github.

From there you probably want to:
- Remove the pre-existing posts in `_posts`
- Change the url in `_config.yml`
- Edit `_includes/sidebar.html` to get your own bio
- Edit `_data/theme.yml` with all the information you want to setup, read through the whole thing as well.
- Change the logo and favicons, just replace the logo with your own picture. However the favicons are slightly harder, I would suggest going to the [Favicon Generator](http://realfavicongenerator.net) website and upload your logo to have it resized for all the platforms and have all the favicon html code generated for you. Then just open up the `_layouts/default.html` file and replace the `<link rel="shortcut icon" href="/favicon.png">` with the code you just generated.
- Then lastly but probably most importantly start writing some posts. I highly recommend [prose.io](www.prose.io), it is a Content Editor for all of your Github repositories but it has support for Jekyll based websites and blogs, just authorize it and navigate to `_posts` within your repository and create a new post.
