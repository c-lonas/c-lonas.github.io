---
layout: post
title:  "DevLog 1 - Editor HUD Part I"
date:   2023-12-16 0
categories: jekyll update
---

## Overview 

_Note: Due to starting this DevLog a few weeks after actually starting the project, the first few posts are retroactive_



Create a HUD to create tile maps in Editor Mode.

I'm not going to walk through every step and every node, I'm going to try to paint a more general picture of the process and decisions being made. If you're working on a similar project and are stuck on something I didn't explain (either I didn't explain it in detail, or I just explained it poorly) feel free to reach out on Discord and I'll help out if I can.

### Requirements
*  select generation shapes 
*  select tile type 
*  include toggles for drawing debug 
*  include toggles for tile info

### Goal
*  Get comfortable with the basics of working with UI elements in UE5

## End Result

Show a screenshot and one to two sentence description of what is accomplished here

<iframe width="560" height="315" src="https://www.youtube.com/embed/vvPpoy3IkXU?si=acOwShKW-w_gpCqK" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Starting off

I used [this video](https://www.youtube.com/watch?v=YCQ1heoaILY) as a reference set up a basic UI widget with a canvas.



<br>

Following along with the video, I created this HUD blueprint and UI Widget. Note that we create a variable that holds a reference to that UI Widget, here labeled `Level_Editor_UI_Ref`. This is how we'll interface with the UI from our other systems (ie the Tile Manager).
![HUDElement](/static/editor-hud-pt1-1-assets/HUD-1.png)

<br>

To facilitate more ergonomic interaction between the Tile Manager and the HUD, I created a simple function to return a reference to the UI. 

![GetLevelEditorHUDRef_Function](/static/editor-hud-pt1-1-assets/GetLevelEditorHUDRefFunction.png)


Here's an example of how this function can access variables and elements from the UI.

![GetLevelEditorHUDRef_usage_example](/static/editor-hud-pt1-1-assets/GetLevelEditorHUDRef_usage_example.png)


## Making HUD stuff and options
At this point I started putting together the actual UI elements on the Canvas panel (this is the WB_UI we created previously). 
This is just a combination of basic `TextBlock` elements, `ComboBox` elements for the drop down menus, and `SpinBox` elements to select values for X and Y. 

![CanvasElements](/static/editor-hud-pt1-1-assets/CanvasElements1.png)

To make these `ComboBox` elements (drop down menus) functional, we need a few things:

* Set up an `On Selection Changed` event for the `ComboBox`- Self-explanatory

* A local variable that is of the type of the existing enumerator you want to use (if you don't already have one, you need to make one)- in this case, I set a variable `ActiveDisplayShape` of type `E_Hex_Shapes`

![ActiveDisplayShapeVariable](/static/editor-hud-pt1-1-assets/ActiveDisplayShapeVariable.png)

* The `Switch on String` node- This is a little clunky having to manually fill in array elements corresponding to the enum elements, but it is what it is. Each of these output pins is then used to `Set` the `ActiveDisplayShape` variable to the appropriate value. The Event Graph for the UI now looks like this:

![SwitchOnString](/static/editor-hud-pt1-1-assets/SwitchOnStringNode.png)


* Now we can bring it all together. From our Tile Manager event graph we call the `GetLevelEditorHUDRef` function to get the necessary variables from the HUD- the Active Display Shape, the X and Y values to be used in that shape, and the Active Tile Type (the type of terrain that should be generated). Because the Line shape requires different generation logic than the other shapes, a switch statement is used to route Line separately from the other shapes. The coordinates for the shape to be generated are created by taking the axial coordinate of the hex that is currently being hovered and the X and Y coordinates taken from the SpinBox in the HUD. Finally, we just loop through the array holding the coordinates of the shape to be generated, and spawn a tile of the appropriate type.


![SpawnTiles](/static/editor-hud-pt1-1-assets/spawntiles.png)


## Hooking up the HUD to the tile generation logic

## Bonus

ChatGPT is awesome for generating Color Palettes.

I prompted it with a list of Biomes I wanted to represent and a brief description of what styles I wanted it to try, and it produced the following table

![ChatGPTColorPalettes](/static/editor-hud-pt1-1-assets/ChatGPTColorPalettes.png)

Then it's a simple matter of copying and pasting the hex codes in to create representations of the color palettes in game. Then you can swap different color palettes in and out for easy testing, it's fantastic.

![ColorPalettesBP](/static/editor-hud-pt1-1-assets/ColorPalettesBP.png)