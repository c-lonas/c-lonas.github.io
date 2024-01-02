---
layout: post
title:  "DevLog 3 - Tilemap Persistence"
date:   2023-12-21 1
categories: jekyll update
---

## Overview 


In this step we add persistence to the Tile Map (Saving and Loading). Since the tiles are all currently generated at runtime, the data is lost when you exit Play mode, and you need to start over every time.

> I'm not going to walk through every step and every node, I'm going to try to paint a more general picture of the process and decisions being made. If you're working on a similar project and are stuck on something I didn't explain (whether I skipped it, I didn't explain it in detail, or I just explained it poorly) feel free to reach out on Discord and I'll help out if I can.

<span style="color: cyan"> Note: Due to starting this DevLog a few weeks after actually starting the project, the first few posts were written retroactively </span>

### Persistence Requirements

Here are the main features and functionalities we implement in this step

*  `Save` Button that stores the TileMap data
*  `Load` Button to re-generate the TileMap using the saved data 

### Learning Goal

* Understand the basics of Persistence in UE5

<br>

## End Result

This is a demo showcasing Tile Map persistence functionality (saving and loading).

![EndResultDemoGif](/static/3-tilemap-persistence-assets/TileMapPersistence720.gif)

<br>

## Starting off

I gave the page on <a href="https://docs.unrealengine.com/5.3/en-US/saving-and-loading-your-game-in-unreal-engine/" target="_blank"> Saving and Loading Your Game</a> from the UE5 docs a quick look, but it didn't really answer the specific questions I had. If the bright screen hurts your eyes, they have a dark mode you can toggle if you click on the three vertical dots next to the 'Search Documentation' box.

<br>

## Initial (Failed) Attempt

The thought process behind the original attempt was fairly straightforward. Unreal Engine has the `Save Game Object`, so I figured we create a `SaveGame_TileMap` blueprint class, in which we create a variable that mirrors the structure of the TileMap. In this case, I created a variable called `SG_TileMap` a map of `Int Point` keys to `E_TileType` values

![SG_TileMapVariable](/static/3-tilemap-persistence-assets/SG_TileMapVariable.png)

<br>

Then I tried to basically copy the TileMap over to the SG_TileMap. 

<span style="color: magenta"> This attempt did NOT work, do NOT use this approach <span>
![IncorrectSavingApproach](/static/3-tilemap-persistence-assets/IncorrectSavingApproach.png)

<br>

## Ask and Ye Shall Receive

After barking up the wrong tree for awhile, I reached out to @Erades on the Hex Grid Toolkit discord, where they kindly set me on the correct path.

The key error I was making was attempting to save the tiles as instantiated actors, which is, apparently, not possible. Instead the correct approach was to loop through the TileMap, and grab just the relevant data (the coordinates and the tile type) to save.

![CorrectSavingAndLoadingApproach](/static/3-tilemap-persistence-assets/CorrectSavingAndLoadingApproach.png)

<br>

## Closing Thoughts

I originally planned on having different 'Save Slots' and then you would choose what slot you wanted to load from, but the level building requirements are going to remain somewhat ambiguous until I test the main movement mechanics, so I'm not going to spend time on superfluous features until I'm sure what's needed.

The main thing we need right now is the ability to have a level that's ready to go for basic testing purposes, so you can load in and test other features without needing to do tile generation everytime. We could cut out an additional step by having it auto-load the previously saved TileMap whenever you press play, but for the time being I like the flexbility of being able to decide at runtime if I want a fresh slate or not. And, as demonstrated in the 'End Result' gif, mission accomplished! Thanks again Erades!