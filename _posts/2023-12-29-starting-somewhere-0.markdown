---
layout: post
title:  "Devlog 0 - Starting Somewhere"
date:   2023-12-29 08:40:20 -0800
categories: jekyll update
---


## Overview

Worked on a different version of this game idea in the past in Unity, some major conceptual changes in this iteration.

The game draws inspiration from a few disparate sources
- Open world, sandbox 
<div class="tenor-gif-embed" data-postid="21973619" data-share-method="host" data-aspect-ratio="1.77778" data-width="50%"><a href="https://tenor.com/view/zelda-breath-of-the-wild2-breath-of-the-wild-the-legend-of-zelda-gif-21973619">Zelda Breath Of The Wild2 GIF</a>from <a href="https://tenor.com/search/zelda-gifs">Zelda GIFs</a></div> <script type="text/javascript" async src="https://tenor.com/embed.js"></script>

- Narrative driven progression

- Survival stuff

* time stuff

The concept of using time as not only a resource but as a currency of sorts is directly inspired from the 2011 sci-film film [In Time](https://en.wikipedia.org/wiki/In_Time)
<div class="tenor-gif-embed" data-postid="23363545" data-share-method="host" data-aspect-ratio="1.82857" data-width="50%"><a href="https://tenor.com/view/intime-arm-timer-gif-23363545">Intime Arm Timer GIF</a>from <a href="https://tenor.com/search/intime-gifs">Intime GIFs</a></div> <script type="text/javascript" async src="https://tenor.com/embed.js"></script>

- Platform Fighters 

Specifically Super Smash Brothers Melee.
Fun and intuitive to use as a beginner and/or a casual player, but a nearly limitless skill ceiling that enables fast and rewarding movement and gameplay options.
<div class="tenor-gif-embed" data-postid="4690309711854426166" data-share-method="host" data-aspect-ratio="1.76596" data-width="50%"><a href="https://tenor.com/view/melee-ssbm-ssb-melee-fox-melee-fox-gif-4690309711854426166">Melee Ssbm GIF</a>from <a href="https://tenor.com/search/melee-gifs">Melee GIFs</a></div> <script type="text/javascript" async src="https://tenor.com/embed.js"></script>


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

## Engine

Reasons for using Unreal
- Mostly just wanting to try something different than Unity
- For visual scripting, Blueprints is native to Unreal whereas Bolt is tacked onto Unity
- For traditional scripting, I've worked a little with C# in the past and I think picking up a little C++ sounds fun