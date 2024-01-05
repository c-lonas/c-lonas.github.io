---
layout: post
title:  "DevLog 7 - Relative Vertex Movement"
date:   2024-01-05 1
categories: jekyll update
---

## Overview 

Hooray! This is the first entry to the DevLog that is being written in realtime.



<br>

## End Result

Insert `End Result` gif here

<br>

## Starting Off

We're going to build off the progress in the previous entry, <a href="don'tforgettoaddthereallink" target="_blank">initial vertex based movement</a>

Starting with the `TriggerSweepToVertex` custom event we set up, we're going to add a condition which for now we're just going to hardcode here in the blueprint- later this might be a different set of hotkeys, or a toggle, or something else.

Off that toggle, we're eventually going to need some very similar logic to what we implemented before with `GetVertexWorldLocation` (which I'll now re-name `GetAbsoluteVertexWorldLocation` to distinguish between what we'll make here in this entry) and `SweepCharacterToVertex`, but before we do that we'll need to write some code to get the character's current vertex, and based on that vertex and the input key event, determine what vertex's location needs to be retrieved for the `lerp` end point.

Something like this

![StartingOff](/static/7-relative-vertex-movement-assets/StartingOff.png)

## Heading




<br>

## Heading



<br>




## Wrapping Up





## Other Thoughts

