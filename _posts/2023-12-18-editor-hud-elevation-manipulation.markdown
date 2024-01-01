---
layout: post
title:  "DevLog 2 - Editor HUD Elevation Manipulation"
date:   2023-12-18 0
categories: jekyll update
---

## Overview 


In this step I create an Editor Mode HUD in order to create tile maps while adjusting input parameters from the UI. Prior to this step, generating tile maps required going into the blueprints, manually making changes, recompiling, and then running to see the result.

> I'm not going to walk through every step and every node, I'm going to try to paint a more general picture of the process and decisions being made. If you're working on a similar project and are stuck on something I didn't explain (whether I skipped it, I didn't explain it in detail, or I just explained it poorly) feel free to reach out on Discord and I'll help out if I can.

_Note: Due to starting this DevLog a few weeks after actually starting the project, the first few posts were written retroactively_

### HUD Requirements - Elevation Manipulation

Here are the main features and functionalities I wanted to add to the HUD in this step:

*  Ability to select type of elevation manipulation (ie random, plateau, etc.)
*  Display (only) the correct parameters appropriate for the type of Elevation manipulation

### Learning Goal

*  Iterate through and apply changes to portions of the TileMap

<br>

## End Result

This is a demo showcasing the progress that was made in this entry. I demonstrate the draw shape toggle, resizing the shape with the X and Y Spinboxes, selecting different shapes, and selecting different tile types to generate. After completing the steps below, I hooked it all up to a `Key Event`, where it takes in the input parameters as determined by the HUD elements and then uses those to actually generate the Tile Map. 

This demo gif showcases the progress that was made with this entry. I demonstrate using the Elevation Manipulation

![EndResultDemoGif](/static/2-editor-hud-elevation-manipulation-assets/EditorModeHUD-ElevationManipulation750.gif)

<br>

## Starting Off

The work in this entry builds heavily off of the previous entry, [Double Check this syntax from the deployed version](/jekyll/update/2023/12/16/editor-hud-tilemap-generation.html)


notes- randomizer and plateau all good, parabola not really getting desired effect- rather than troubleshoot this, we'll keep moving with minimum viable product for now until we get to the key thing, which is proof of concept on the core gameplay mechanics. No sense worrying about specific terrain adjustment stuff that may or may not be relevant