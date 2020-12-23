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

## Technical Implementation

### Part weight
The weight of all parts that consist only of normal ABS plastic can be calculated relatively easily.
We can calculate the volume using the method described in [this paper](http://chenlab.ece.cornell.edu/Publication/Cha/icip01_Cha.pdf)
or use a library like the [GNU Triangulated Surface Library](http://gts.sourceforge.net/).

We can get the weights of each brick directly using the [BrickLink Catalog Download](https://www.bricklink.com/catalogDownload.asp).
This is the only way to get the correct volume for all parts which contain non-ABS materials.

### Connections between parts
A lot of information about how the parts can be connected is already available in the LDraw parts library.
All parts are composed of primitives. [The Primitive Reference](https://www.ldraw.org/library/primref/) lists them all.
Unfortunately not all connections can be derived from primitives. For example the underside stud of a 1x1 brick isn't made from primitives.
Therefore, we need a list to add additional connections.

This component can later be reused for part snapping.

### Data Structure
It's better to not use the element tree directly as the data structure. It should be simplified to a collection of parts
because physics do not care about the part hierarchy of a model, and the code would just be unnecessarily complex. 

