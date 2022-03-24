---
title: 'Whip Game Physics'
date: 2022-03-01
permalink: /posts/2022/03/WhipGamePhysics/
tags:
  - Physics
  - Whip Mechanics
  - Energy Conservation
  - Kinematic Equations
  
---
 Not done.

What Problem did you Have?

I need to make a whip weapon and it does not look good using traditional animation techniques like bones.

What Steps did you take to solve it?

Started looking for information on procedually generated geometry and bezier curves with which to construct a whip out of in code.

I found a tutorial on generating a race track by extruding a 2d mesh along a bezier curve.

What did you learn in the process?

I learned that you can do animation inside of shaders and that it I will likely be able to do the whip animation using generated geometry fed 
into the a special effects shader graph. And then I'll likely be able to use a new VFX feature which is making connecting particles into  strings. 

I learned that setting up procedural geometry might be worth it because, although the intial setup is long, the automation it provides is well worth it.


Part II

What Problem did you have?

I need to make a whip that move realistically enough that it is visualyl pleasing and satisfying to crack a whip on something. The issues is that the actual movement of a whip is currently a higly unsolved problem in physics so I had to start theorizing about how to go about this.

I found out during my research that whip mechanics is a HIGHLY unsolved problem, and now I know why no one puts actual whips inside of video games. I have a theory on how this could possibly work involving Energy Conservation and Bezier Curves. It will get more complicated later, but for now I'll just focus on how fast a whip can go based purely on Energy Conservation and its remaining moving mass.

I'm Modeling a whip as a circle that is thrown towards a target and consumes the leangth of the whip as it propagates until it runs out of length to consume. 

WHIP ANIMATION GOES HERE
[Whip Velocity Animation](https://cattoisland.github.io/files/WhipCircleVelocity.mp4) 

This circle propagation is the Group Velocity of the whip. Any other shapes that the whip may have gotten from the whipping motion are highly irrelevant to this speed and will only change Z directional offesets that are not related to the group velocity of the whip which im calling Circle Velocity.

I watched a lot of whip videos and they all look like there is a shape that is frozen in place and just travels down the length of the rope along the rope while slowly attenuating. This shape gradually loses its amplitude and it likely make some contribution to the group-velocity of the whip but its not as large as the overall velocity of the whip, so for now I'm ignoring it. The average Dispalcement of the whip is conserved and the impuse that is applied to it simple travels downwards all the way to the end. If physics operated perfectly you could likely send a square wave or even a pointy triangle down a whip. However because of being a physical item the whip does have physics, elasticity and dampening.

When we observe whips we see that they mostly propagate a sine wave or circle down its length and never actually a pointy shape like a square or triangle or impulse function. My thinking is that the input motion from a hand is like an  input function to the whip via its handle and then the whip itself acts like a low pass filter that has a transfer function and filters out all frequences from the input function that are too high a frequency to propagate along the rope.

INSERT PICTURE OF WHIP BEHAVING AS LOW PASS FILTER

What did you learn from it?

I learned that with a little extra effort that just making an attack animation the regular way, I will likely end up with a very satisfying whip mechanic that will be very unique to this game. Hopefully it will be well worth the effort and deserving of having a combat system built around it. 


