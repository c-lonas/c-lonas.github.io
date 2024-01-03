---
layout: post
title:  "DevLog 4 - Basic Character Movement"
date:   2023-12-27 1
categories: jekyll update
---

## Overview 

With basic controls in place to create and manipulate a Tile Map, time to shift gears for a bit and get a character in play to get closer to our short-term goal of being able to prototype core movement mechanic concepts.

<span style="color: cyan"> Note: Due to starting this DevLog a few weeks after actually starting the project, the first few posts were written retroactively </span>


### requirements
* Implement basic character locomotion


### goals
* Understand the basics of Character Movement in Unreal Engine 5


## End Result

Insert `EndResult` demo gif here

<br>

## Starting Off

The progress in this entry ended up being pretty straightforward, I basically just followed along with this <a href="https://docs.unrealengine.com/5.0/en-US/setting-up-character-movement" target="_blank"> Setting Up Character Movement Guide</a> from the UE5 docs.

<br>

# Migrating from Axis and Action Mappings

I followed along with the tutorial and got things working, but I did see this warning when setting up the bindings:

![AxisAndActionMappingsDeprecatedWarning](/static/4-basic-character-movement-assets/AxisAndActionMappingsDeprecatedWarning.png)


So I'm going to try to migrate those over.


[Enhanced Input Documentation](https://docs.unrealengine.com/5.3/en-US/enhanced-input-in-unreal-engine/)


I'm not positive, but I think the Enhnaced Input features will ultimately be helpful for the movement system I have in mind, so to begin with, we'll just migrate over one action to test it out.

The documentation here is good, but it holds your hand a little less the 'Setting Up Character Movement Guide' listed above, so I'll fill connect the dots a little here. You know, in case your hand is getting cold.

![HoldingHandsGif](/static/4-basic-character-movement-assets/holding-hands.gif)

We'll start with Jumping, so I'll disconnect the Jump node from the previous setup. This is more or less what you'll have after following along with the 'Setting Up Character Movement Guide'.

![DisconnectLegacyJump](/static/4-basic-character-movement-assets/DisconnectLegacyJump.png)

Next we're going to need two things:
1. An `Input Action`, and
1. An `Input Mapping Context`