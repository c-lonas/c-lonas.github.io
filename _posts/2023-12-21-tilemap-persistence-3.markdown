---
layout: post
title:  "DevLog 3 - Tilemap Persistence"
date:   2023-12-21 1
categories: jekyll update
---

## Overview 


In this step we add persistence to the Tile Map (Saving and Loading). Since the tiles are all currently generated at runtime, the data is lost when you exit Play mode, and you need to start over every time you start.

I originally planned on having different 'Save Slots' and then you would choose what slot you wanted to load from, but the level building requirements are going to remain somewhat ambiguous until I test the main movement mechanics, so I'm not going to spend time on superfluous features until I'm sure what's needed.

The main thing we need right now is the ability to have a level that's ready to go for basic testing purposes, so you can load in and test other features without needing to do tile generation everytime. We could cut out an additional step by having it auto-load the previously saved TileMap whenever you press play, but for the time being I like the flexbility of being able to decide at runtime if I want a fresh slate or not.

> I'm not going to walk through every step and every node, I'm going to try to paint a more general picture of the process and decisions being made. If you're working on a similar project and are stuck on something I didn't explain (whether I skipped it, I didn't explain it in detail, or I just explained it poorly) feel free to reach out on Discord and I'll help out if I can.

<span style="color: cyan"> Note: Due to starting this DevLog a few weeks after actually starting the project, the first few posts were written retroactively </span>

### Persistence Requirements

Here are the main features and functionalities we implement in this step

*  `Save` Button that stores the TileMap data
*  `Load` Button to re-generate the TileMap using the saved data 

### Learning Goal

*  Get comfortable with the basics of working with UI elements in Unreal Engine 5

<br>

## End Result

This is a demo showcasing persistence functionality (saving and loading) for the Tile Map.

![EndResultDemoGif](/static/3-tilemap-persistence-assets/TileMapPersistence720.gif)

<br>

## Starting off



## Attempt 1

This attempt did NOT work


## Attempt 2

Erades explained how we can't actually save the Tile objects, instead we just save the data we need from them (ie coordinates and tile type)


