---
title: Personal Voice Assistant
layout: category-post
categories: zeos
published: false

---

A while back my Google Home assistant gave out on me and after not having it for a while I got the idea of making my own assistant.

But in the early beginnings the plan wasn't that grandiose, it was more humble than that. I wanted a simple python app that could run smaller scripts on a schedule, each script being on its own schedule and everything (which would check up on Youtube subscriptions, Spotify podcasts etc).

But I soon learned about a python library that can control most if not all of IKEA's Trådfri eco-system, which is their smart home system for lights, power outlets and more. Which could replace one of the main uses that the Google Assistant had been doing for me.

So suddenly my assistant wasn't just doing scheduled scripts but could now also execute so called *jobs*. which is what I call the scripts that you have to execute manually (by a button press or a voice command).



## To flesh out:

- the IKEA FYRTUR curtains that is also connected to the Trådfri eco-system.
- Nest of applications (master and slaves, basically acting as remotes to the master)
- Living in the system tray



https://github.com/Uberi/speech_recognition

https://www.simplifiedpython.net/speech-recognition-python/

https://github.com/ggravlingen/pytradfri

Live in the system tray http://www.blog.pythonlibrary.org/2013/07/12/wxpython-how-to-minimize-to-system-tray/