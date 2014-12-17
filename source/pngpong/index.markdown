---
author: admin
comments: true
date: 2010-12-15 03:18:48+00:00
layout: page
slug: pngpong
title: PNGpong
wordpress_id: 200
---

![](http://ryanschenk.com/wp-content/uploads/2010/12/icon.png)

PNGpong is a Dashboard widget I created  to optimize PNG files. You can download it [here](http://ryanschenk.com/wp-content/uploads/2010/12/PNGpong.zip). It is not [a cross-browser solution for displaying transparent PNGs](http://blog.psyrendust.com/pngpong/).

PNG is a wonderful file format that suffers from an unfortunate gamma problem ([details here](http://hsivonen.iki.fi/png-gamma/)). PNGpong alleviates this issue by stripping the color "correction" information out of the file using pngcrush. PNGpong then attempts to further compress the PNG file by running it through optipng (I say "attempts" because some PNG's may already be as compressed as possible).

Simply drop one or more PNG files onto PNGpong and it'll take care of the rest. To drop a file onto a Dashboard widget, first depress the mouse button on the desired file and begin to drag the icon. While still holding down the mouse button, push the Dashboard hot-key on your keyboard. This will activate Dashboard while you are still dragging the file and allow you to drop the icon onto the PNGPong widget.

By default, PNGpong will create a new optimized file with "_PONGED" on the end of the filename. If you would like, there is a preference to overwrite the original file instead.

PNGpong is not much more than a convenient UI for the command line tools pngcrush and optipng, with some nice graphics I made in Photoshop.
