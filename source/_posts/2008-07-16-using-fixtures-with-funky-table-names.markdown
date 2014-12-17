---
author: admin
comments: true
date: 2008-07-16 15:18:21+00:00
layout: post
slug: using-fixtures-with-funky-table-names
title: Using Fixtures with Funky Table Names
wordpress_id: 3
tags:
- Fixtures
- Rails
- RSpec
- Ruby
---

If you have an AR Model whose table name does not follow the convention, and you have needed to set it explicitly using `set_table_name`.




    
    
    class ChiliDog < ActiveRecord::Base
      set_table_name 'dogs_made_of_chili'
    end
    





Then your test fixtures file must be named the same name as the **table**, not the model...


`dogs_made_of_chili.yml`



In your rspec, you must use the **table** name to call your fixtures, then specify the AR class that models it...



    
    
    fixtures :dogs_made_of_chili
    set_fixture_class :dogs_made_of_chili => 'ChiliDog'
    





Note that little guy `set_fixture_class`!! He does not appear in the online Rails API docs (at least not [Rails Brain](http://www.railsbrain.com/)), so I had originally assumed that you would pass in a Constant, not a String to it. I was wrong!!





The class name given to set_fixture_class must be a **String** and not a Constant like you might assume/think/wish-for/hope/desire. If you put a constant in there, you will get all sorts of weird, will bang your head against your desk repeatedly, pull your hair, tear your clothes, pour ashes on your head, and various other Old-Testament-style lamentations.





So, word of warning, use a String, not a Constant when using `set_fixture_class`!
