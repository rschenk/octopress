---
author: admin
comments: true
date: 2011-12-02 16:17:58+00:00
layout: post
slug: breedlight
title: Breedlight
wordpress_id: 234
categories:
- Art
---



{% img center /images/2011-12-02-breedlight/breedlight-web-logo.gif %}

**_Update!_ I was [interviewed on NPR](http://www.wgbhnews.org/post/lamps-sex-lives-blend-science-and-design) about Breedlight!** I go into detail about the Breedlight project, how it works, and the artistic motivation behind it, as well as my thoughts on art, design, and engineering. Please [have a listen](http://www.wgbhnews.org/post/lamps-sex-lives-blend-science-and-design)!

Breedlight is a series of sculptural lamps that I've been working on, whose design is dictated by a genome that I created. Breedlight lamps are capable of reproducing with each other, passing on their traits to future generations of interior lighting.

{% imgcap center /images/2011-12-02-breedlight/breedlight-showcase-9-1.jpg 333 500 Breedlights at TEDxWoodsHole %}

Each lamp has a unique genetic code—a DNA of sorts—that describes its size and shape. Although I make the lamps, I do not design them. I breed them from other Breedlight lamps! Breeding happens inside software that I wrote for this purpose, which can run on the web and in mobile phones.

{% img center /images/2011-12-02-breedlight/chromosome.png %}

Each lamp's traits are contained in a single chromosome, shown above, comprised of 20 genes. These 20 genes encode the size and shape of the Breedlight lamp. Its height, width, and the prevalence and shape of its curves are all described by these genes. Breedlight lamps with two different shapes will have correspondingly different chromosomes to manifest those physical differences.

I chose the chromosome model to enable two lamps to reproduce with each other, passing on their their genetic material and physical traits to their offspring. This works very much like in real life: to reproduce, each parent lamp splits its chromosome, independently assorts the genes, and contributes half its genetic material to the offspring. The offspring receives a half-chromosome from each parent, combining them to form a full chromosome. Laws that I've encoded in the genome determine how the traits inherited from each parent combine and contribute to the offspring's physical form.

{% img center /images/2011-12-02-breedlight/Breeding.gif %}

Consider the example breedings above, showing the children of lamp A♥B on the left, and B♥C on the right. Note that lamp B, which features a bulge in the middle is in both breedings. As you can see, most of the children in both of these breedings inherit the central bulge from lamp B. The children on the left tend to be wider and squatter, which they inherit from lamp A; the children on the right tend to be taller and skinnier, which they inherit from lamp C. These heritable traits are the genes at work, but because the chromosomes are split randomly, there is variation among the children.

{% img center /images/2011-12-02-breedlight/breedlight-showcase-6.jpg %}

A Breedlight's genetic information is encoded into a QR code, which functions like their DNA. This code can be scanned by a smartphone to launch the Breedlight software, which I wrote to run on mobile phones and in the browser. The software reads the chromosomes of one or more Breedlights, renders the shapes, and allows a customer to breed any two lamps by tapping or clicking on them.

{% img center /images/2011-12-02-breedlight/breedlight-mobile.gif %}

On the backend, the software renders vector outlines of a Breedlight in SVG. I use this file to cut out the forms that the Breedlights are built upon. If I had access to a CNC machine, I could programmatically generate toolpaths from this file, and send it out to be cut; unfortunately, I don't have a CNC machine, so the forms get cut by yours truly and a jigsaw.

{% img center /images/2011-12-02-breedlight/IMG_4213.jpg %}

From there, I place the form in a jig that I made, and construct the lamps in the traditional manner of a Japanese chochin lantern. This process is results in some fantastic looking lamps, but is very labor intensive, and when making one-off designs like I am, wasteful of materials. Future developments for Breedlight will be focussed on making the construction process efficient, but more importantly ensuring the materials truly embody the artistic sensibilities of the project. These lamps are organisms, given life by a computational environment, and I am actively seeking out materials and processes that express these traits to the fullest extent.
