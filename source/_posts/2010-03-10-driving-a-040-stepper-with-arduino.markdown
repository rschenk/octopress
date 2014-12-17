---
author: admin
comments: true
date: 2010-03-10 23:31:16+00:00
layout: post
slug: driving-a-040-stepper-with-arduino
title: Driving a $0.40 Stepper with Arduino
wordpress_id: 134
---

I recently bought 250 stepper motors (part number 21-02485-03) for a sculpture that I'm working on, for the low price of [40 cents a piece](http://www.goldmine-elec-products.com/prodinfo.asp?number=G14197B)! Even if you don't buy them in bulk, they are still [really cheap](http://www.goldmine-elec-products.com/prodinfo.asp?number=G14197).

There are [several](http://www.goldmine-elec.com/pdf/G14197.pdf) [driver](http://profmason.com/?p=173) [circuits](http://www.picaxe.orconhosting.net.nz/stepdemo.jpg) [available](http://www.instructables.com/id/Drive-a-Stepper-Motor-with-an-AVR-Microprocessor/) for this motor, which were very helpful in figuring out the strange wiring inside this motor. However, none of the above drivers played nicely with the [Arduino Stepper Library](http://arduino.cc/en/Reference/Stepper), which uses [Tom Igoe's stepper driver circuit](http://www.tigoe.net/pcomp/code/category/code/arduinowiring/51). It took an evening to figure out how to connect this stepper to Tom's driver and the Arduino stepper library, so I thought I would post it here.

The first step is to cut the white wire, which turns the stepper from a weird hybrid into a normal bipolar stepper. The links above will explain this in more detail if you're curious.

The next step is to correlate the four wires on the motor to Tom Igoe's circuit and the Arduino stepper library. These use the [numbers 1-4](http://www.tigoe.net/pcomp/code/category/arduinowiring/51) to describe the wires coming out of the motor, and order _does_ matter. With the 21-02485-03, the wires numbered 1-4 correlate to the Red, Blue, Yellow, and Black wires respectively. 

With this knowledge we can easily hook up our stepper to Tom's circuit and start using the Arduino Stepper Library immediately. Here's a diagram of [Tom Igoe's 4-wire circuit](http://www.tigoe.net/pcomp/img/stepper-bipolar-hbridge.jpg), with the Arduino code after it. The IC chip used is a [L293D H-Bridge](http://www.solarbotics.com/products/l293d) and note that the notch in the IC faces to the right (a bit hard to tell).

[![](http://ryanschenk.com/wp-content/uploads/2010/03/Stepper-Driver_bb-300x125.png)](http://ryanschenk.com/wp-content/uploads/2010/03/Stepper-Driver_bb.png)
Image developed using [Fritzing](http://fritzing.org/).


    
    /* 
    
      Drives the 21-02485-03 Stepper Motor attached
      to Tom Igoe's four-wire driver circuit
      
    */
    
    #include <stepper.h>
    
    
    // Change these to the pin numbers of each color wire 
    #define YELLOW  8
    #define RED     9
    #define BLACK   10
    #define BLUE    11
    
    #define SPEED 200 // RPM
    
    
    #define LED_PIN 13
    
    // create an instance of the stepper class, specifying
    // the number of steps of the motor and the pins it's
    // attached to
    //
    // Order matters here when giving it the pins
    Stepper stepper(20, RED, BLUE, YELLOW, BLACK);
    
    
    void setup()
    {
      // set the speed of the motor to 30 RPMs
      stepper.setSpeed(SPEED);
      
      pinMode(LED_PIN, OUTPUT);
    }
    
    void loop()
    {
      
      stepper.step(100);
      delay(300);
    
      stepper.step(-100);
      delay(300);
    }
    




