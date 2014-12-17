---
author: admin
comments: true
date: 2008-07-31 16:49:16+00:00
layout: post
slug: controlling-whitespace-with-haml
title: Controlling Whitespace with HAML
wordpress_id: 14
---

When displaying certain elements as inline, the whitespace between tags **does** matter in your layout.

When trying to display some `LI` tags as inline, I really needed to spit out the tags with no whitespace in between. Unfortunately [HAML](http://haml.hamptoncatlin.com/)s handy-dandy tag indenting was wrecking me. It was so bad, that I resorted to calling a helper method that spat out the HTML as a string, with no whitespace between the tags.

But today, I discovered that if you append the HAML 'tag' with a "`>`", it will not add any whitespace to the tag.

Example:

    
    
    %ul.filter_navigation.tabnav
      %li.go.first>= link_to_function 'Gene Ontology', 'Filter.select("go")'
      %li.age>=      link_to_function 'Longevity',     'Filter.select("age")'
      %li.gaz.last>= link_to_function 'Gaz Ontology',  'Filter.select("gaz")'
    


Results in this HTML:

    
    
    <ul class="filter_navigation tabnav"><li class="go first"><a href="#" onclick="Filter.select("go"); return false;">Gene Ontology</a></li><li class="age"><a href="#" onclick="Filter.select("age"); return false;">Longevity</a></li><li class="gaz last"><a href="#" onclick="Filter.select("gaz"); return false;">Gaz Ontology</a></li></ul>
    



No Whitespace! You got a date Wednesday baby!
