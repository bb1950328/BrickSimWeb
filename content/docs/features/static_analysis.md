---
title: "Static Analysis"
weight: 2
---
## Vision
Imagine designing a large bridge with LEGO(R) parts. 
Wouldn't it be useful if you could see whether your construction is robust before you order the parts?
Depending on that, you might even find a better solution that is stronger, uses fewer parts, or looks better.

All that should be possible - if you have the right software.
Unfortunately, there's currently no software capable of doing a physics analysis of a LEGO model.  
BrickSim will change that.

## Plan / Ideas
* The analysis model is just another object inside the element tree. The user can
    * hide it
    * delete it
    * enable automatic recomputing if his computer is fast enough or his model small enough
* If the element is visible, the bricks should be displayed in rainbow colors over the original bricks (red means high stress, green means low stress)

