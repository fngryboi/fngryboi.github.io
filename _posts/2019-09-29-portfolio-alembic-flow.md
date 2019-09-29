---
title: Alembic Animation in UE4 (Portfolio)
layout: category-post
tags: portfolio
published: true
---

**Under construction...**

This is a little peek on a on-going project that I'm working on, where I used Realflow to create a liquid animation for testing purposes within UE4.

<video width="1920px" height="1080px" controls muted>  <source src="/assets/video/portfolio/WatermarkedAlembic.mp4" type="video/mp4">  <source src="/assets/video/portfolio/WatermarkedAlembic.ogg" type="video/ogg"></video>

The main animation was created in Realflow that consists of the main domain, a circular spline shape that was created from the letter "O", Daemons for the physics that attracts the liquid along the spline with an added Noise Field component for some visual randomness, there's also a Drag component to make sure that the liquid doesn't stray away from the spline. The Dyverso emitter used for the liquid is turned off about half-way. 

The liquid animation was then rendered to mesh form using the Particle MESH VDB component and then exported as an alembic file (.abc), this was then compressed using Blenders Decimate modifier with the goal of shrinking the filesize without losing too much detail for a game scenario.