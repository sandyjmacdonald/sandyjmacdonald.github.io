---
layout: post
title: Explorer HAT Pro
date: 2015-02-24 12:00:00
summary: Build a Lights Out game with Explorer HAT Pro.
tags: ["raspberry pi","python","pimoroni","explorer hat","explorer hat pro","tutorial"]
visible: 1
---

I teased the [Explorer HAT](http://shop.pimoroni.com/products/explorer-hat)
in my write-up of my
[visit to Pimoroni](http://sandyjmacdonald.github.io/2015/02/19/a-visit-to-pimoroni/).
Explorer HAT and its bigger, meaner brother Explorer HAT Pro are little breakout
boards that have a mini breadboard in the middle, 4 capacitative touch buttons along
the bottom edge, 4 metal capacitative touch pads along the left hand edge and a bunch
of IO pins, including analog input and motor output on the Pro version. You'll see my
prototype version of Explorer HAT Pro below (the final version is on a black PCB, of course).

![Explorer HAT Pro]({{ site.url }}/assets/explorer_hat_pro.jpg)

The possibilities for Explorer HAT are endless. It's sort of like the spiritual
successor to the Pibrella, with more LEDs, more buttons and more IO pins, plus breakout
pins for a lot of the GPIO pins on the Rapsberry Pi.

Some ideas that I've had for mini projects with Explorer HAT Pro include:

* A simple version of the Lights Out game (more on that below)
* A reaction time game
* A visual thermometer, using a temperature sensor and the built-in LEDS
* A PIN code entry system

I'll probably post the latter three up in the next week or so, once I've finished
writing the code. In the meantime, here's a fun little game that you can download
and try on your new Explorer HAT (or Explorer HAT Pro).

# Lights Out

[Lights Out](https://en.wikipedia.org/wiki/Lights_Out_(game)) is a simple game where
the aim is to turn out all of the lights by
toggling them on and off. Usually, the lights are in a 5x5 grid but there's no
reason why you can't do it with grids of other sizes or even a single row of lights,
as we have here. Obviously, it's easier with a row of just 4 LEDs, but fun nonetheless.

The game works as follows. It starts by randomly turning on some or all of the lights.
If you tap a light that is on, it toggles off and conversely, if you tap a light
that is off, it toggles on. Simple. However, when you toggle a light, the adjacent lights
(in this case the ones on either side) also toggle to the opposite of
their current state. The game is over when all of the lights are out. The aim is to
complete the game in as few moves as possible.

Here it is in action:

{% include embed_video.html param="http://www.youtube.com/embed/l2j14fyTqUQ" %}

I've added the game to [my fork](https://github.com/sandyjmacdonald/explorer-hat) of
the Pimoroni Explorer HAT library. You can download it, install, and run it as follows:

```bash
git clone https://github.com/sandyjmacdonald/explorer-hat.git
cd explorer-hat/library
sudo python setup.py install
cd ../examples
sudo python lights_out.py
```

You may also need to `curl get.pimoroni.com/i2c | bash` and
`sudo apt-get install python-smbus`.

The code is really simple, thanks largely to the convenient `explorerhat.light[i].toggle()`
method that toggles a light to its opposite state. All we have to do is periodically check
the state of the 4 LEDs with a while loop:

```python
while len(light_nums) > 0:
	explorerhat.touch.pressed(toggle_light)
	light_nums = [i for i in range(0,4) if explorerhat.light[i].is_on()]
	time.sleep(0.05)
```

And then we trigger a `toggle_light` function that toggles that LED, and the adjacent ones,
when a touch is detected by `explorerhat.touch.pressed()`:

```python
def toggle_light(channel, event):
	if channel > 4:
		return
	if event == 'press':
		global num_moves
		num_moves += 1
		explorerhat.light[channel-1].toggle()
		if channel == 1:
			explorerhat.light[channel].toggle()
		elif channel == 4:
			explorerhat.light[channel-2].toggle()
		else:
			explorerhat.light[channel-2].toggle()
			explorerhat.light[channel].toggle()
		print 'You have taken %i moves so far. Keep going!' % num_moves
```

We also have a couple of extra bits that check the number of moves taken, randomly
pick the LEDs that are switched on at the start, and print a message and flash the
LEDs in a pretty pattern when you've won.

Stay tuned for more Explorer HAT Pro projects in the coming weeks!
