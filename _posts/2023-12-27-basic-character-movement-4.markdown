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
* Add Elevation options 


### goals
* Understand the basics of Character Movement in Unreal Engine 5


## End Result

Insert `EndResult` demo gif here

<br>

## Starting Off

The progress in this entry ended up being pretty straightforward, I basically just followed along with this <a href="https://docs.unrealengine.com/5.0/en-US/setting-up-character-movement" target="_blank"> Setting Up Character Movement Guide</a> from the UE5 docs.

# Migrating from Axis and Action Mappings

I followed along with the tutorial and got things working, but I did see this warning when setting up the bindings:

![AxisAndActionMappingsDeprecatedWarning](/static/4-basic-character-movement-assets/AxisAndActionMappingsDeprecatedWarning.png)


So I'm going to try to migrate those over so I have something to write up in this entry besides just follow the guide in the link above.