---
layout: post
title: The Explorer HAT Pro parts kit
date: 2015-05-26 12:00:00
summary: Everything you need to get started with your Explorer HAT Pro.
tags: ["raspberry pi","python","pimoroni","explorer hat","explorer hat pro","parts kit"]
---

The Pimoroni [Explorer HAT Pro](http://shop.pimoroni.com/products/explorer-hat)
has quickly become my favourite Raspberry Pi HAT. 
It's such a versatile bit of kit, with its digital inputs and outputs, analog inputs,
motor outputs, capacitive touch and breadboard, the possibilites are endless.

I've been putting together a few tutorials for the swish new 
[learn.pimoroni.com](http://learn.pimoroni.com) page. More about them below. 

I've also given some input on what to include in a parts kit to go along with the 
Explorer HAT or Explorer HAT Pro. It has lots of simple components that you can 
use to put together some fun projects with your Explorer HAT.

[The kit](http://shop.pimoroni.com/products/explorer-hat-pro-parts-kit)
comes in a smart little metal tin; handy for keeping it all together or carrying it 
around with you.

![Parts kit closed]({{ site.url }}/assets/explorer_hat_parts_kit_1.jpg)

And here are all the bits laid out.

![Parts kit open]({{ site.url }}/assets/explorer_hat_parts_kit_2.jpg)

And here's a list of everything that comes in it.

* 16x LEDS - 4 of each Yellow, Red, Blue and Green
* 1x Piezo Transducer
* 10x 470 Ohm Resistors
* 5x 10k Ohm resistors for pulling up Explorer Hat’s outputs
* 2x 10k rotary potentiometers
* 1x SN74HC595N Shift Register
* 2x 0.1uF Ceramic Capacitor
* 1x TMP36 Analog Temperature Sensor
* 20-way Male to Male Jumpy Jerky Jr.

# PIN entry system

A few weeks back, I published a [tutorial](http://learn.pimoroni.com/tutorial/sandyj/explorer-hat-explorer-hat-pin-entry) 
on how to set up a fun little PIN entry system with some of the bits from the
parts kit.

Here's a little video of the PIN entry system.

{% include embed_video.html param="http://www.youtube.com/embed/bgQsK5e_2Hw" %}

# 8-bit shift register

And earlier tonight, I published another [tutorial](http://sandyjmacdonald.github.io/2015/05/26/shift-register/)
showing how you can use an 8-bit shift register to drive lots of LEDs, driving 8
output pins from just 3 of Explorer HATs output pins. All of those bits are also in the parts kit.

Check out the blinkiness!

{% include embed_video.html param="http://www.youtube.com/embed/0AlbIEaZJEw" %}

# More to come...

I'll be putting together more of these tutorials with the Explorer HAT Pro parts kits in 
the coming weeks. To tease you, I'm working on a simple one that will use the rotary
potentiometer to control some LEDs, and a more advanced one that builds a visual
thermometer with the TMP36 analog temperature sensor.

Also, I've been working with Pimoroni on a series of plugins that you can call from the
Explorer HAT Python library to make it really easy to use the components in the parts
kit (and others in the near future) with your Explorer HAT. The shift register is just the
first of these.

In the meantime, just [buy one](http://shop.pimoroni.com/products/explorer-hat-pro-parts-kit)!
Seriously, just [buy one](http://shop.pimoroni.com/products/explorer-hat-pro-parts-kit)!

{% include twitter_plug.html %}