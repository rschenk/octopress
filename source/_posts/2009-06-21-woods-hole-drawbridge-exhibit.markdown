---
author: admin
comments: true
date: 2009-06-21 19:13:24+00:00
layout: post
slug: woods-hole-drawbridge-exhibit
title: Woods Hole Drawbridge Exhibit
wordpress_id: 91
categories:
- Art
---

Several weeks ago I was approached to contribute an art installation to an upcoming show at the [Woods Hole Historical Museum](http://www.woodsholemuseum.org/) commemorating the Woods Hole drawbridge. Our drawbridge, originally installed in the late 1930's, was replaced with a new one this winter. The show is centered around two time lapse movies that document the entire demolition of the old bridge and construction of the new one. There is also a documentary film about the old bridge, historic photographs, and my project.

I was given the old control box to the bridge, and turned it into an interactive "virtual bridge" installation. The control box is a 40lb metal contraption, with a set of industrial buttons on the face, and a huge nest of wires on the inside. The buttons lights up, each one containing its own 120vac-to-6v step down transformer to power the bulb. Also interesting is the mechanical aspect of the button is a separate module from the electrical contacts. Normally-open or normally-closed electrical contact modules are screwed onto the back of the button module, I assume so one can replace the contacts when they wear out.

[caption id="" align="alignnone" width="500" caption="Buttons inside the Control Box"][![Buttons inside the Control Box](http://farm4.static.flickr.com/3601/3630752333_c16392565d.jpg)](http://www.flickr.com/photos/ryanschenk/3630752333/)[/caption]

Attached to the buttons was a huge mess of wires, which ran out of the box through a conduit. When the bridge was operational, this conduit connected to some sort of logic unit that was lost during demolition. Having talked to bridge operators, and given the vintage of this control system, I suspect the logic was performed with a large bank of relays.

To create a computer input controller for the virtual bridge, my friend Dan ripped out the original wiring, and re-wired just the 120vac circuit to make all the buttons light up. Next, I got the controller to interface with the computer. To do this, I used the USB keyboard encoder hack. This is a very easy technique, accomplished by opening up a keyboard, plugging it in, and shorting pins on the keyboard encoder circuit. With a little trial-and-error, you can determine a set of combinations that reproducibly "type" specific key codes into the computer. For instance, shorting a certain two pins on the encoder might always type the letter "w" onscreen. I came up with one pin combination for each of the buttons on the control box, soldered on some wire leads, and connected them to the buttons on the control box.

[caption id="" align="alignnone" width="500" caption="USB keyboard circuit wired to the control buttons"][![USB keyboard circuit wired to the control buttons](http://farm4.static.flickr.com/3648/3630753599_c8f1851b2f.jpg)](http://www.flickr.com/photos/ryanschenk/3630753599/)[/caption]

Once I had the control box talking to the computer, the rest was done in software. The idea for the installation was simply to "create a virtual drawbridge," so I had quite a bit of creative freedom. Initially, I was given video footage of the bridge in operation, and I experimented with using the control box to manipulate video playback. I really wanted the control box to perform realtime [datamoshing](http://www.youtube.com/watch?v=6LG39Wp7OzQ) on the bridge video, but ultimately this proved unfeasible and way too weird for the (elderly) population of Woods Hole.

Instead, I scrapped the video footage entirely and used Flash to create a bridge tending video game. Museum patrons – with the aid of onscreen prompts – use the real control box to operate an animated drawbridge, allowing cars to drive over and boats to sail under. The game required quite a bit of illustration, which is not really my forte, but came out looking great. While I had originally designed the game for kids, during the opening reception it was a bigger hit with old people than children! I suspect these folks have been wanting to play with that bridge controller for years, and now they finally can.

[caption id="" align="alignnone" width="500" caption="Screenshot of the Drawbridge Video Game"][![Screenshot of the Drawbridge Video Game](http://farm4.static.flickr.com/3570/3636788331_b1a63d8984.jpg)](http://www.flickr.com/photos/ryanschenk/3636788331/)[/caption]
