---
layout: post
title: Roberts R600 refurb
date: 2017-02-17 22:00:00
summary: Refurbishing a 50-year old Roberts R600 and adding a Pi Zero running Volumio.
tags: ["raspberry pi","pimoroni","making","refurb","electronics"]
visible: 1
---

Just this past week, I've finished a refurb of a vintage Roberts R600 radio. The
original radio wasn't working, although the speaker was, so I decided to give
the whole thing a thorough overhaul. The Pimoroni ARRR600 was born!

![](/assets/ARRR-600-1.jpg)

I completely gutted it, removing all but the speaker, the wooden housing, and
the metal chassis that held the top panel in. I laser-cut a new top panel, added
new buttons and two new rotary potentiometers with brushed aluminium knobs, and
even laser-cut a new logo for the front.

![](/assets/ARRR-600-4.jpg)

The brains of the new radio was a
[Pi Zero](https://shop.pimoroni.com/products/raspberry-pi-zero)
with Wi-Fi dongle, a
[Speaker pHAT](https://shop.pimoroni.com/products/speaker-phat) DAC/amp. to
drive the speaker, and an [Enviro pHAT](https://shop.pimoroni.com/products/enviro-phat)
to read the analog values from the rotary potentiometers (for volume and tuning)
using its ADC.

You can read more about the project in my post on the Pimoroni blog
[here](http://blog.pimoroni.com/the-pimoroni-arrr600-radio/).
