---
layout: post
title: Development Blog
cover: chile_glacer.jpg
categories: posts
---

## Video Games

### CAG - Godot


### Daily Log

#### March 5th, 2024 - Vectors and rotations
I've been working through figuring out how to set up an AI routine to control the spaceships. This is proving to be another challenge, in that vector systems are complicated... Turns out when dealing with RigidBody3D objects, there really are two spatial systems at play. The global one representing the spacial mapping of the scene and the relative or basis of the RigidBody3D, think of this as the self reference axis. This helps determine self direction, think looking to your left as opposing to tell someone to look north. At least that is how I was able to understand it. Anyway, this learning fixed my rotation issue as the rotation functions were applying rotations in the global coordinates instead of the relative ones. So I need to figure out a way to get relative rotational torque vectors. This hasn't been easy so far as no searching has provided with straightforward solutions so I'm attempting to draw out the solution myself. Crossing my fingers! 

At least there was progress these past two days, I can direct an AI to rotate a ship towards it's target with the correct orientation. Also I've confirmed my usage of Signals in Godot is correct! And I've got a selection system in place for only controlling one ship at a time, however given the red vectors in one the screenshots, you can see I still have work to do. I also updated the skybox and ambiant light to a more bright yellow to make it more clear than the purple.
![Successful rotation]{{ '/images/Screenshot 2024-03-05-1.png' | prepend: site.baseurl }}
![Two vector arrow]{{ '/images/Screenshot 2024-03-05-2.png' | prepend: site.baseurl }}

#### March 3rd, 2024 - Starting a blog to track and document
Due to my friend Zack's suggestion, I am starting to log and keep track of my work in video game development. 

I've had this game idea for some time, I worked on designing the core concepts about a year ago. Most documentation
for this was kept in white boarding apps like Lucid Charts or Miro (I can't remember which one I used for this, I haven't
referred back to it in a while due to me learning the basic of game development). I'll try to get that linked in here some day.

At the moment, I've settled on using Godot 4.0, mainly due to ease of use on my laptop. I tried learning and building some basic stuff
on my desktop. This mostly was learning Unity for some time before they had their PR/billing policy issues. I started to explore Unreal
and found it taking longer to learn. I did want to keep trying as it finally was a good motivation to learn C++. But since all of this work
was on my desktop, I couldn't find enough time to work and retain my learnings. I then was gifted a laptop (Macbok) and have since found more time I can be
working on it. I tried Swift/Xcode tools for ipad development but found myself needing to build basic game development tools, so I tried Unreal
on my laptop but it was too much to run. So I finally tried Godot and found it to work well with what I learned from Unity and Unreal, 
as well as being lightweight enough for my laptop to run.

With that, I build a simple Scene using a prebuilt spaceship asset. Built so lighting in and some skybox decoration, then built simple
space controls. Next was figuring out how vectors work to get a good directional vetor of movement since understanding how my
ship was moving in this void was hard without a relative measure or object providing direction. So I added both a measure (a red arrow) and
a shape to stay at the origin. It works well enough to move to the next step of scripting AI!

I've got a screenshot of the arrow and shape for reference.
![Vector Reference Arrow]{{ '/images/Screenshot 2024-03-03.png' | prepend: site.baseurl }}

