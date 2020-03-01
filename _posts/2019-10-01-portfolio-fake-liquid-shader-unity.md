---
title: Fake Liquid Shader in Unity
layout: post
categories: gamedev
published: true
---

This is a demonstration of my first major ShaderGraph (Unity's Material Editor) attempt at making a fake liquid volume using that was also capable of producing waves. The code that drives the waves isn't doing it physically correct by any means, but I still believe it came out great despite the short amount of time that I spent on it.

<video width="1920px" height="1080px" controls loop muted controlsList="nodownload">
    <source src="/assets/video/gamedev/FakeLiquidShaderGraphUnity.mp4" type="video/mp4">
    <source src="/assets/video/gamedev/FakeLiquidShaderGraphUnity.ogg" type="video/ogg">
</video>

This setup utilizes two 3D objects, one for the glass itself and then another for the liquid volume inside of it. The liquid volume is a child object of the glass to make it move relative to the glass. The liquid material then basically cuts off the 3D mesh to be the amount of liquid desired, and the "top-face" you see is actually the inside of the 3D mesh. The liquid section then has an optional foam part (if there is any foam amount it will automatically make the top face the same color as the foam), and the rest of liquid can be configured in any way imaginable using anything from a simple color, gradient or even an external shader.

This works since it's more of a cell-shaded/flat look that is reminiscent to The Legend of Zelda: The Wind Waker with the colors being fully opaque. If it were transparent there would be visual glitches as well as having certain parts overlap which both would break the illusion.

*Note: This project was originally composed during the spring of 2019*