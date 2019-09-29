---
title: Alembic Animation in UE4
layout: category-post
categories: portfolio
published: true
---

This is a little peek on a on-going project that I'm working on, where I used Realflow to create a liquid animation for testing purposes within UE4.

<div class="video_wrapper">
    <video width="1920px" height="1080px" controls muted controlsList="nodownload">
     	<source src="/assets/video/portfolio/WatermarkedAlembic.mp4" type="video/mp4">
        <source src="/assets/video/portfolio/WatermarkedAlembic.ogg" type="video/ogg">
    </video>
</div>

The main animation was created in Realflow that consists of the main domain, a circular spline shape that was created from the letter "O", Daemons for the physics that attracts the liquid along the spline with an added Noise Field component for some visual randomness, there's also a Drag component to make sure that the liquid doesn't stray away from the spline. The Dyverso emitter used for the liquid is turned off about half-way. 

The liquid animation was then rendered to mesh form using the Particle MESH VDB component and then exported as an alembic file (.abc), this was then compressed using Blenders Decimate modifier with the goal of shrinking the filesize without losing too much detail for a game scenario.

Then I made a simple transparent liquid material with some simple vertex animations that animate over the mesh, which is then elevated with the refraction effect to really bring home the realistic liquid look.

This is something that I hope to use by looping alembic animations for certain scenarios where that's possible, allowing me to pre-render animations and not have to worry about unforeseen outcomes that I've experienced with Realtime Fluid Solvers (such as Nvidia FLeX), or having to do some material trickery that only work so far.

This method will work in controlled scenarios, for example in a cutscene or a water fountain. It's more manual work but I believe the end result is worth it.