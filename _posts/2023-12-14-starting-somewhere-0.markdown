---
layout: post
title:  "DevLog 0 - Starting Somewhere"
date:   2023-12-14 0
categories: jekyll update
---

<span style="color: cyan"> Note: Due to starting this DevLog a few weeks after actually starting the project, the first few posts were written retroactively </span>
## Overview


The game draws inspiration from a few disparate sources

<br>
* Open world, Sandbox

<div class="left-text-right-media">
    <div>
        Add Description Here
    </div>
    <div>
        <img src="/static/0-starting-somewhere-assets/zelda-breath-of-the-wild.gif" alt="BreathOfTheWild-OpenAdventureGif"> 
    </div>
</div>

<br>
* Narrative driven progression
<div class="left-text-right-media">
    <div>
        Add Description Here
    </div>
    <div>
        <img src="/static/0-starting-somewhere-assets/firsttree.webp" alt="TheFirstTree"> 
    </div>
</div>
<!-- - Survival stuff -->

<br>
* Time theme
<div class="left-text-right-media">
    <div>
        The concept of using time as not only a resource but as a currency of sorts is directly inspired from the 2011 sci-film film <a href="https://en.wikipedia.org/wiki/In_Time" target="_blank"> In Time </a>
    </div>
    <div>
        <img src="/static/0-starting-somewhere-assets/intime-arm-timer.gif" alt="InTimeArmTimer"> 
    </div>
</div>

<br>
* Platform Fighters 
<div class="left-text-right-media">
    <div class="left-text">
        Specifically Super Smash Brothers Melee.
        Fun and intuitive to use as a beginner and/or a casual player, but a nearly limitless skill ceiling that enables fast and rewarding movement and gameplay options.
    </div>
    <div>
        <img src="/static/0-starting-somewhere-assets/melee-fox-oscar.gif" alt="MeleeMovement"> 
    </div>
</div>



<br>
* * * 
<br>

Yes, I realize there is inherent tension between some of these sources- my hope is that the tension is productive in creating unique gameplay loops and forcing interesting design decisions. Each of those potentially interesting design decisions also represents fresh opportunities to shoot myself in the foot here, so I'm not quitting my day job.



<br>
## Hex stuff
The single best resource on hexagons and hexagonal grids is the blog from Red Blob Games, aka [The Hexagon Bible](https://www.redblobgames.com/grids/hexagons/)

### Hex Grid Toolkit 
Since the underlying formulas for working with hexagonal grids are consistent and solved (see above) there isn't a lot of room for creativity or problem solving here, so I went with a pre-built asset to give me something to work with. After testing out two assets, I went with the [Hex Grid Toolkit](https://docs.google.com/document/d/1vsdGHcBz8xxV_BukaKuX3oRfeKAMaYkkOwvTUjwyikM/edit), which is a fairly un-opionated library of hex-related functions. 

This made it easier to jump into learning the Unreal Engine environment by having something with which to play around.

<br>

## Engine

Reasons for using Unreal
- Mostly just wanting to try something different than Unity
- For visual scripting, Blueprints is native to Unreal whereas Bolt is tacked onto Unity
- For traditional scripting, I've worked a little with C# in the past and I think picking up a little C++ sounds fun