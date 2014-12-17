---
author: admin
comments: true
date: 2009-03-02 21:13:11+00:00
layout: post
slug: ligercat-released
title: LigerCat Released
wordpress_id: 83
---

I have been working on version 2 of the LigerCat tool since October. Today, we flipped the switch and turned it on, at [http://ligercat.ubio.org](http://ligercat.ubio.org).

LigerCat is the brainchild of [Dr. Neil Sarkar](http://www.uvm.edu/~insarkar/), and was created by me. 

It's hard to explain its use to someone outside the scientific or medicine field, but I'll try my best to break it down. 

The basic idea is that "tagging" is nothing new. The Web 2.0 folks got the idea from librarians, who have been tagging literature for many years. Librarians "tag" things using a "controlled vocabulary," which is just a set of tags that are curated and maintained by some authoratative body. For instance, scientific articles published in life sciences field are tagged with a controlled vocabulary called Medical Subject Headings (MeSH), which has over 20,000 tags in the set.

The problem is, the journals that publish these articles are not annotated with MeSH descriptors; journals are annotated with another controlled vocabulary called Journal Subject Terms...but there's only 120 of them! So, an article is published in a journal. This article could be tagged with any number of 20,000 MeSH descriptors. However, the journal that publishes the article is only tagged with one or more of the 120 Subject Terms.

That seems silly, doesn't it? 

That's where LigerCat comes in. It can find every article published in a journal, and is capable of generating a tag cloud of the MeSH terms applied to every article published in a journal. The National Library of Medicine has a database of life sciences articles called PubMed, so we downloaded all the records, and built indices from that.

From a journal's MeSH tag cloud, you can click one or more tags. LigerCat will do a live search back to PubMed to see the articles tagged with your selections. 

That's pretty cool to begin with, but there's a lot more that we can do with the technology. 

The articles tab will allow you to do a plain old search into the PubMed article database. Ligercat will download all the results, and build a MeSH tag cloud from the articles returned by your search. You can search for a [topic](http://ligercat.ubio.org/articles/biodiversity%20informatics), a [person](http://ligercat.ubio.org/articles/Shimomura%20O), or an [organism](http://ligercat.ubio.org/articles/Cavia%20porcellus), and LigerCat will build you a MeSH cloud based on the results.

Or you can go nuts, and click over to the Genes tab. You can paste a FASTA-formatted sequence of ATC's and G's into the text box. ([This is a good one to try if you're curious](http://www.ncbi.nlm.nih.gov/nuccore/41406056?report=fasta).) LigerCat uses an algorithm called BLAST to find all the known genes that are similar to the one you pasted. LigerCat will use its own magic to find all the articles written about those genes, then display a MeSH cloud built from all those articles. You could start with an unknown gene sequence, and in the span of a few minutes, be reading articles about that sequence. Pretty neat stuff.

For the geeks reading this, you may notice that the searches to PubMed are performed live outside the HTTP request/response cycle. I used [BackgrounDRB](http://backgroundrb.rubyforge.org/) to pull this off, and it works quite well. If and when LigerCat experiences a lot of load, BackgrounDRB will allow us to pull the background search workers off onto their own server(s), allowing us to isolate the computationally intensive part of the application away from the app server.
