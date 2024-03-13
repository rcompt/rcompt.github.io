---
layout: post
title: Development Blog
cover: chile_glacer.jpg
categories: posts
---

## Video Games

### CAG - Godot


### Log

#### March 12th, 2024 - Polishing up Vectors and Rotation, plus a little AI
Turns out it was a much more simplier answer to get the proper rotational vectors! The basis vectors were all I needed as they were already stored in the global coordinate reference, which makes sense once I learned what they stood for. With that figured out, I did play around a little more with the AI system and found there was an issue with my conditional logic. However, I really didn't like building out a whole logic system through a bunch of 'if' statements, so I went exploring online and found this system built for Godot that should be a more structure approach to AI development that is scalable. It is called Beehave, it wasn't too hard to install in my game. Luckily it seems Godot have been built around easy expansion! 

The main goal with my AI at this time is to have it control the ship with the same controls I would have to use. So this means we both are sending a signal to apply a force to the ship and then have to apply an equal force at a time to stop the moment. The AI will have the advantage of a system telling it the exact math to handle more complicated movements (two or three rotational axes at once). Anyway, I figure it will be sometime before my next update as this little goals usually take longer than I expect.

Here are some screenshots of me playing around with the ship and conduct a rendezvous with them! Then I rotate around and continue to verify the rotational vectors are correct, I was very relieved when they continued to do so!

![Successful rendezvous](https://github.com/rcompt/rcompt.github.io/blob/master/images/Screenshot%202024-03-12-1.png?raw=true)<img src="drawing.jpg" alt="drawing" width="734"/>
![Successful rotation at rendezvous](https://github.com/rcompt/rcompt.github.io/blob/master/images/Screenshot%202024-03-12-2.png?raw=true){width=734}

#### March 5th, 2024 - Vectors and rotations
I've been working through figuring out how to set up an AI routine to control the spaceships. This is proving to be another challenge, in that vector systems are complicated... Turns out when dealing with RigidBody3D objects, there really are two spatial systems at play. The global one representing the spacial mapping of the scene and the relative or basis of the RigidBody3D, think of this as the self reference axis. This helps determine self direction, think looking to your left as opposing to tell someone to look north. At least that is how I was able to understand it. Anyway, this learning fixed my rotation issue as the rotation functions were applying rotations in the global coordinates instead of the relative ones. So I need to figure out a way to get relative rotational torque vectors. This hasn't been easy so far as no searching has provided with straightforward solutions so I'm attempting to draw out the solution myself. Crossing my fingers! 

At least there was progress these past two days, I can direct an AI to rotate a ship towards it's target with the correct orientation. Also I've confirmed my usage of Signals in Godot is correct! And I've got a selection system in place for only controlling one ship at a time, however given the red vectors in one the screenshots, you can see I still have work to do. I also updated the skybox and ambiant light to a more bright yellow to make it more clear than the purple.

![Successful rotation](https://github.com/rcompt/rcompt.github.io/blob/master/images/Screenshot%202024-03-05-1.png?raw=true)
![Two vector arrow](https://github.com/rcompt/rcompt.github.io/blob/master/images/Screenshot%202024-03-05-2.png?raw=true)

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
![Vector Reference Arrow](https://github.com/rcompt/rcompt.github.io/blob/master/images/Screenshot%202024-03-03.png?raw=true)

