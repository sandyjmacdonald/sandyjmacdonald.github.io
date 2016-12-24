---
layout: post
title: Visual notifications on the Raspberry Pi
date: 2015-01-26 12:00:00
summary: Build a visual notification system with Unicorn HAT and Skywriter.
tags: ["raspberry pi","python","pimoroni","skywriter","unicorn hat","tutorial"]
visible: 1
---

Here's a nice quick one on how set up a visual notification system with a
couple of Raspberry Pis, a Pimoroni Unicorn HAT LED matrix, Skywriter HAT
3D gesture sensor and a couple of USB wifi adaptors.

The inspiration was the tap notifications on the upcoming Apple Watch. I
realised that you could set up something very similar with the kit above.

![Apple Watch tap notifications]({{ site.url }}/assets/apple_watch_tap.gif)

The end result is pretty awesome and takes next to no time to set up. You can
see it in action below. It'd be ideal for quietly calling someone upstairs
without waking the kids, for example.

{% include embed_video.html param="http://www.youtube.com/embed/4ol272hJSOo" %}

## Setting it up

What you'll need:

* A couple of Raspberry Pis A+ or B+
* A Pimoroni [Unicorn HAT](http://shop.pimoroni.com/products/unicorn-hat)
* A [Skywriter HAT](http://shop.pimoroni.com/products/skywriter-hat)
* A couple of USB wifi adaptors like [these](http://thepihut.com/products/usb-wifi-adapter-for-the-raspberry-pi)

As always, do a `sudo apt-get update` and `sudo apt-get upgrade` to get
everything up-to-date on your Raspberry Pi.

As in my previous tutorials, set up the Unicorn HAT and Skywriter as follows:

```bash
sudo pip install unicornhat
```

and then  

```bash
sudo pip install skywriter
```

Then you can clone the [GitHub repo](https://github.com/sandyjmacdonald/unicorn_notifier)
with the two scripts you'll need by typing:

```bash
git clone https://github.com/sandyjmacdonald/unicorn_notifier
```

I'll presume that you've set up wifi on your Raspberry Pis already, but if not
then it's really easy - just plug in a monitor and keyboard, launch the desktop
by typing `startx` and then set up your wifi to connect to your router there.

You'll need to make a note of the IP address of the Pi into which you've plugged
the Unicorn HAT. You can find it by typing `ifconfig` and then looking under the
`wlan0` section. I set up all of this over SSH, but alternatively you could
plug each Pi into a keyboard and monitor and start the two scripts running
before moving them to wherever they'll be getting used.

On the Pi with the Skywriter attached, the sender, you'll need to edit the line
that says `host = '192.168.0.XX'` and add the IP address that you wrote down
earlier. Then run the script by typing:

```bash
sudo python skywriter_send.py
```

On the other Pi, with the Unicorn HAT on, type:

```bash
sudo python skywriter_receive.py
```

You should see it say `Waiting to receive messages...`.

Now, if everything is working properly, you should be able to tap the centre of
the Skywriter on one Pi and the Unicorn HAT will pulse gently on the other Pi.
There's a touch of latency because the request has to go over wifi between the
Pis, but it's remarkably responsive in my testing.

# A word of warning!

This sends the requests un-encrypted in the open between the
Pis, so make sure that the port that your doing this over, 13000 in my script,
isn't open to the outside world. If you are concerned about this, then you can
send all of the requests over SSH. I won't go into how to do that here, but
Google it if you want to do it that way. The other option is to use a router
that isn't connected to the internet and then security won't be an issue.

# Taking it further

The most obvious improvement for this would be to make it a two-way notification
system. You could set this up with an extra Unicorn HAT and Skywriter and a
couple of [Black HAT Hack3rs](http://shop.pimoroni.com/products/black-hat-hacker).
