---
layout: default
title: Win98 Aesthetic Theme
tags: web
published: true
---

# Win98 Lo-Fi Theme

This theme was inspired by PaladinAmbers stream overlay and created by modifying an existing theme made by [hi](https://github.com/h01000110) called [windows-95](https://github.com/h01000110/windows-95).

![PaladinAmber's Stream Overlay](/assets/images/posts/win98theme/paladinamberstreamoverlay.png)

# Notable Changes:

From the original windows 95 theme

- Updated the icons to Windows 98 styled ones, that are available from [https://win98icons.alexmeub.com/](https://win98icons.alexmeub.com/)
- Added an animated background video with aesthetic vibes, that can be found and changed in /assets/video/. Just replace each file with the ones you like using the same file name and formats (you can find similar ones to the one used by searching for a combination of "aesthetic", "lo-fi". "anime", "80s"...).
  - Beware! For the visitors comfort try to keep the motion to a minimum!
- Updated the windows title bar to use a gradient the same way Windows 98 does
- Updated so it should work when hosting locally for testing
- Changed so the text file naming for each article is on two rows to allow for longer titles of articles (it will break the word and end it in a ellipsis using webkit line clamp)
- Adjustments to the lines in the tag-list in the file explorer part, making it look closer to the original and aligned with everything.
- Fixed so images won't scale beyond the window size so there's no horizontal scroll bar
- Minor changes to responsiveness and bugfixes.

# Todo:

These are the things I'm going to fix before publishing this on a standalone repository for others to download and play around with.

- Add the option to have the original windows 98 gradient using a if statement and a variable in the config file (this will also disable the background video)
  - The user then has the option to use the default Windows 98 style or embrace the Lo-Fi Aesthetic look by a simple change in the config file.
- Fix the repository name to be called "Windows 98 Aesthetic"
- Update the ReadMe.md
- Make it easier to add social links in the top bar using the Jekyll config file
- Added animated background picture, can easily change these as you see fit. Just search the web for any combination of "aesthetic", "lo-fi", "anime" and you should find something you like to use.
- Change tag system to category system so it's neater (?)
- Add RSS feed button to the topbar