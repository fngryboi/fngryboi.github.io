---
title: Fake Liquid Shader in Unity
layout: post
categories: portfolio
published: true
---

This is a demonstration of my first major ShaderGraph (Unity's Material Editor) attempt at making a fake liquid volume using that was also capable of producing waves. The code that drives the waves isn't doing it physically correct by any means, but I still believe it came out great despite the short amount of time that I spent on it.

<video width="1920px" height="1080px" controls loop muted controlsList="nodownload">
    <source src="/assets/video/portfolio/FakeLiquidShaderGraphUnity.mp4" type="video/mp4">
    <source src="/assets/video/portfolio/FakeLiquidShaderGraphUnity.ogg" type="video/ogg">
</video>

This setup utilizes two 3D objects, one for the glass itself and then another for the liquid volume inside of it. The liquid volume is a child object of the glass to make it move relative to the glass. The liquid material then basically cuts off the 3D mesh to be the amount of liquid you want, and the "top-face" you see is actually the inside of the 3D mesh. The liquid section then has an optional foam part (if there is any foam amount it will automatically make the top face the same color as the foam), and then you can put in any colors or even external shaders for the rest of the liquid.

This works since it's more of a cellshaded/flat look that is reminiscent to The Legend of Zelda: The Wind Waker with the colors being fully opaque. If it were transparent there would be visual glitches as well as having certain parts overlap which both breaks the illusion.

The ShaderGraph material used to achieve this can be seen below (although I did have to strip out the gradient colors and bubbles to instead use a solid color to fit it into the screenshot):

![A screenshot of the ShaderGraph material used to achieve the liquid look](/assets/images/posts/fakeliquidunity/fakeliquidunityshadergraph.png)

[Link to the full resolution image.](/assets/images/posts/fakeliquidunity/fakeliquidunityshadergraph.png)

*Word of advice: some variables from the screenshot aren't used in the shader*

To make the waves move all you need to do is attach a script to the glass object (since the liquid is a child of the glass) that takes all the movement into account and drives the WobbleX and WobbleZ variables of the material. Although you don't need to worry about any rotations since the material accounts for those.