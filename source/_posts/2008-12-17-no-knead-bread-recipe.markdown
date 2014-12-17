---
author: admin
comments: true
date: 2008-12-17 19:05:58+00:00
layout: post
slug: no-knead-bread-recipe
title: No_Knead_Bread.rake
wordpress_id: 68
---

#
    # Denali's No-Knead Miracle Bread
    #
    
    require 'cast_iron_dutch_oven'  # sudo gem install dutch_oven --version 3.5 Quart --source KitchenwaresStore
    require 'mixing_bowl'
    require 'spatula'
    
    desc "Step 1. To be performed at night"
    task(:at_night) do
      
      ingredients = { 'Warm Water'        => '2 Cups',
                      'Yeast'             => '1/4 tsp', # Yes, that's all
                      'All Purpose Flour' => '1 Cup',   # King Arthur is the best.
                      'Whole Wheat Flour' => '1/4 Cup' }
      
      MixingBowl.contents = ingredients.collect {|ingredient, amount| ingredient.measure(amount) }
    
      MixingBowl.contents.mix_thoroughly(:with => Spatula)
      
      MixingBowl.cover(:with => :cloth, :loosely => true)
      
      sleep 4.hours..8.hours
    end
    
    desc "Step 2. To be peformed the next morning"
    task(:morning => :at_night) do
      
      ingredients = { 'All Purpose Flour' => "#{(2 + 1/2).scant} Cups",
                      'Asiago Cheese'     => '4 oz',
                      'Salt'              => '2 teaspoons' }
                      
      ingredients['Asiago Cheese'].dice '3/8" cubes'
      
      MixingBowl.contents << ingredients.collect{ |ingredient, amount| ingredient.measure(amount) }
      
      MixingBowl.contents.mix_thoroughly(:with => Spatula)
      
      MixingBowl.cover(:with => :cloth, :loosely => true)
      
      sleep 6.hours..8.hours
    end
    
    desc "Step 3. To be performed after work"
    task(:after_work => :morning) do
      Oven::MiddleRack.contents << DutchOven
      Oven::MiddleRack.contents.insert(DutchOvenCover, :next_to => DutchOven)
      Oven::PreHeat.new(500.degrees)
      
      case Oven::PreHeat.status
      when done? 
        sleep 20.minutes  # Let DutchOven heat up after oven is at temperature
      end
      
      MixingBowl.contents.sprinkle_with :flour
      
      dutch_oven_cover, dutch_oven = Oven::MiddleRack.contents.pop, Oven::MiddleRack.contents.pop
    
      dutch_oven.inside.spray_with :oil
      MixingBowl.contents.roll_into(dutch_oven, :with => WetSpatula)
      
      Oven::MiddleRack.contents << dutch_oven.cover!(dutch_oven_cover)
      
      Oven::Bake.at(475.degrees, 25.minutes)
      DutchOven.uncover!
      Oven::Bake.at(450.degrees, 12.minutes..16.minutes)
      
      Oven::MiddleRack.contents.pop
      
    rescue ThirdDegreeBurnError 
      Oven.turn_off
      raise EmergencyRoomException, "Wear oven mitts next time", caller
    end
