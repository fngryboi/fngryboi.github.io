---
title: Limitless Rooftiles in Unity
layout: post
categories: portfolio
published: true
---

Ever since the first time I saw the scene in Limitless where the pills first activate for Bradley Cooper's character Eddie Morra and he looks up to see rooftiles flip, I've always wanted to try and recreate that in a game engine where you'd also be able to control the output and formatting. A short clip from the scene is shown below:

<video width="1920px" height="1080px" controls loop muted controlsList="nodownload">
    <source src="/assets/video/portfolio/LimitlessRooftilesScene.mp4" type="video/mp4">
    <source src="/assets/video/portfolio/LimitlessRooftilesScene.ogg" type="video/ogg">
</video>

And here's the result from that venture, made in Unity and the shader for the rooftile was done using ShaderGraphs.

<video width="1920px" height="1080px" controls loop muted controlsList="nodownload">
    <source src="/assets/video/portfolio/LimitlessRooftilesUnity.mp4" type="video/mp4">
    <source src="/assets/video/portfolio/LimitlessRooftilesUnity.ogg" type="video/ogg">
</video>

The video demonstrates the two ways the rooftiles can flip, either all of them or just the ones that have a symbol assigned to it. It also showcases some simple examples of alignment (top-right, bottom-left and centered), although the margin is set to 1 on all the examples (meaning there's at least 1 rooftile of space between the text and the walls).

The project is made up of a simple ShaderGraph that renders the corresponding letter given to each tile from a script, the script formats everything to its right place and supports word-wrapping and aligning it where you want it, as well as adding margin around the text. There's also options for which rooftiles flip over, either all of them will flip randomly or just the ones with symbols on it.

Even though the flipping pattern isn't as detailed as the scene in the movie, where it seems to have groups of rows that flip sequentially one after another on each row together with some minor randomness in certain areas. I'm still pleased with the outcome, and who knows - maybe I'll come back to this one and iterate on it before applying it in one of my own games.

*Note: This project was originally composed during the spring of 2019*