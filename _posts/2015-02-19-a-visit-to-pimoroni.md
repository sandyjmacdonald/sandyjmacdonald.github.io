---
layout: post
title: A visit to Pimoroni
date: 2015-02-19 12:00:00
summary: A write-up of my visit to the Pimoroni factory.
tags: ["pimoroni","flotilla","slice","picade","propeller hat","explorer hat","framboisedorf"]
visible: 1
---

A couple of weeks ago, on a frosty Wednesday morning, I got the train down to
Sheffield to visit [Pimoroni](http://shop.pimoroni.com). Jon, the director of
Pimoroni, had invited me to have a chat with them about upcoming products and
about a new learning portal that they're planning to launch soon. I also got to
have a look around their factory floor and see how the well-oiled Pimoroni machine
operates.

Pimoroni is located about 10 minutes walk away from the station, on a small
estate. As soon as I saw the laser-cut sign
with the Pimoroni logo on the fence, I knew I was at the right place. A sign
on the door reads *"Pirates and ninjas and lasers and shit"*. Definitely the
right place.

## Electronics treasure trove

Jon shares an office with Paul -- the other founder of Pimoroni -- and Phil,
a software engineer. The office is like an electronics treasure trove with
boxes full of the new Raspberry Pi 2 (it had just launched on the Monday before
my visit), prototypes of upcoming Raspberry Pi HATs (more on these later)
complete with blinking LEDs, and a Lego Technic model on the window ledge. A
window in the office looks out onto the factory floor with their laser-cutters,
pick-and-place machine, robot lab (where they factory test their products)
and stock for their online shop. It's an
impressive setup for a company that started out just a couple of years ago
making perspex cases for the Raspberry Pi, in what Jon tells me amounted to a
garage, and now they're designing and making their own PCBs in their own
factory.

Chatting with Jon, Paul and Phil, it seems like the Pimoroni crew are all
multi-talented and work in close collaboration on the hardware, design and
software for their products. I guess that's the best way to ensure that it
all works well together and it gives them complete control over the quality
of their products.

Above all, what's apparent is that they care deeply about getting every detail
right. For example, Jon explained to me about how they found a local company
that would powder-coat the wood panels for their
[Picade](https://www.kickstarter.com/projects/pimoroni/picade-the-arcade-cabinet-kit-for-your-raspberry-p)
mini arcade cabinet because it gave a finish similar to that used in the old
full-size arcade cabinets. They also showed me a prototype of
[Slice](https://www.kickstarter.com/projects/fiveninjas/slice-a-media-player-and-more)
 -- their Raspberry Pi compute module-powered media player -- which Jon and Paul are
working on as part of a new venture called FiveNinjas Ltd. Paul showed me the
machined and anodised, red almunium case that will house Slice, and pointed out
a tiny, flat part on the rounded corners of the casing (I could barely see it).
He explained that that they weren't happy with this and were having new gold
master prototypes made before approving the final design. The details matter.

## Learning portal

Recently, Pimoroni have been talking to a few makers that have been producing
content that showcases their products with a view to opening an online learning
portal. The portal would have interesting and fun projects that you can get up
and running fairly quickly, written by selected contributors and curated by
Pimoroni.

From my point of view, it would help the contributors, like me, to get their
content seen by a larger audience and, for Pimoroni, I guess it would show
customers cool ways to use their products.

I think Jon and co. are still working out the logistics of it but I told them
that I was happy to migrate my content across to the portal as soon as it
launches.

## Flotilla

In case you missed it, Flotilla is Pimoroni's latest Kickstarter project. It's
a collection of modules that plug into a central dock via custom made USB
cables, or ropes as Pimoroni calls them. The dock connects to the Raspberry Pi
(in fact, you can connect up to four docks to one Raspberry Pi) and deals
with all of the IO from the modules. There are inputs -- a range of sensors,
dials, switches -- and outputs -- LED displays, motors, and more -- that you can
link together through the dock to do cool stuff.

![Flotilla]({{ site.url }}/assets/flotilla.png)

Again, there are some beautiful little details included. Jon showed me a little
perspex disk that will sit on top of, and protect, the dock PCB and had the
Flotilla anchor logo printed on it. The PCBs for all of the modules will be
in a range of different colours. They're even having the USB cables that
link the modules to the dock custom made with little anchors printed on the
micro USB connectors.

I was given a demo of Flotilla working with the custom-designed web app,
Rockpool (image below), that allows you to chain together inputs and link them to outputs,
even including basic logic. In a few seconds, we had created a simple setup
where an LED lit up if both a button was toggled and the slider was moved. Flotilla
was impressively complete given that, at that stage, the Kickstarter funding
hadn't yet finished.

![Rockpool]({{ site.url }}/assets/rockpool.jpg)

It seems like Flotilla might be a game-changer when it comes to education,
but I can also see it appealing to families who want to teach their kids how
to program. Having said that, I think Flotilla is powerful enough to allow
adults to create some quite complex setups in a short amount of time while
not worrying too much about the hardware/software headaches that you
inevitably get with traditional Raspberry Pi or Arduino prototyping.

## HATs

HATs have become a big part of what Pimoroni do. HATs (Hardware Attached on
Top) are addon boards for the Raspberry Pis A+/B+/2 that all conform to a
number of specifications, including size, drawn up by the Raspberry Pi
foundation. Pimoroni's first was the
[Unicorn HAT](http://shop.pimoroni.com/products/unicorn-hat), an 8x8 neopixel
LED matrix, which I absolutely love and for which I've written a number of
[tutorials]({{ site.url }}/tags/#unicorn+hat). Since, they've released the
[Skywriter HAT](http://shop.pimoroni.com/products/skywriter-hat), a 3D
gesture-sensing addon. They don't rest on their laurels though.

I got to see four new HATs that Pimoroni are currently prototyping. The first
is Explorer HAT, a bit of a jack-of-all-trades. They'll have two models: the
Explorer HAT, and Explorer HAT Pro (left, below) which will have some extra capabilities.
I've been playing with a prototype and it really is an incredible piece of kit.
In the centre of the board is a space for a mini breadboard to connect all sorts
of things to your Explorer HAT. Along the bottom edge are four capacitative touch
pads and four differently coloured LEDs. Along the left edge are four metal
capacitative touch pads that you can attach crocodile clips to and then connect
to bananas, oranges, lychees, or whatever. There are also a number of IO pins,
including analogue input pins (the board had an ADC built in) and motor output pins.
I'll have a post in the next couple of days with some mini-projects that you can
try with your Explorer HAT Pro when it launches soon.

![Explorer HAT Pro and Propeller HAT]({{ site.url }}/assets/explorer_propeller.jpg)

The next was Propeller HAT (right, above). The Parallax Propeller is an 8 core processor which,
in the context of Propeller HAT, can deal with IO simultaneously in parallel on
its 8 cores without the traditional interrupts. In layout, Propeller HAT is
similar to Explorer HAT, with a mini breadboard in the centre and IO pins around
the edges. The meat in the Propeller HAT/Raspberry Pi sandwich is the Python
library and IDE which allow you to compile and upload code to the Propeller. Phil
gave me a demo of the Propeller HAT playing some (extremely loud) SID tunes,
full of synth-y polyphonic goodness. The beauty of Propeller HAT is the ability
to simultaneously control a bunch number of IO pins (28) at once.

I've often yearned for a tiny piano or synth controller that I could fit in
my pocket. Soon my yearning will be no longer. Framboisedorf (I think I got
that right) is a capacitative touch piano HAT. Apparently, it's named in
homage to the Austrian piano makers Bösendorfer. It has an octave of keys and,
if I remember correctly, a couple of other keys that you can use for other
things like raising/lowering the octaves. As always with the Pimoroni HATs,
it's beautifully designed, with the Framboisedorf logo along the top in a
perfectly appropriate Gothic typeface just like the Bösendorfer logo.

Last was the Narwhal HAT. Narwhal HAT is basically the same as Unicorn HAT
except that it uses the DotStar APA102C LEDs rather than the NeoPixel WS2812B
LEDs. The advantages of these DotStar LEDs is that they don't have a specific
timing requirement like the NeoPixels and can handle faster PWM, presumably
giving faster refresh rates. The disadvantage is cost, as the DotStar LEDs cost
significantly more than the NeoPixels. I'm hoping that Pimoroni decide to
release the Narwhal HAT anyway, despite the cost.

## Errata

If you're ever in Sheffield, then I'd highly recommend the
[Street Food Chef](http://www.streetfoodchef.co.uk) for some tasty Mexican food.
I had the chicken mole burrito and it was scrum-diddly-umptious.

Also, on the way to the station, I dropped in to
[Tamper Coffee](http://tampercoffee.co.uk/sellers-wheel/) (the one at Sellers Wheel,
next to Sheffield Hallam University) and got myself a very tasty flat white and
millionaire's shortbread. Again, I'd highly recommend it.

And last, but not least, stay tuned for some more tutorials...

*Flotilla images courtesy of Pimoroni.*
