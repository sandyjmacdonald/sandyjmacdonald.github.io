---
layout: post
title: Average selfie
date: 2017-09-17 20:00:00
summary: Averaging 130 selfies taken over 18 months into an "average selfie".
tags: ["photography","python"]
visible: 1
---

Here's something I did ages ago but never got round to writing up. I think it's
really cool, so I wanted to share it with you. It's an average selfie!

Using the iPhone app
[Everyday](https://itunes.apple.com/us/app/everyday/id398081659?mt=8), I took
130 photos of myself over a period of about 18 months. The app's great. It
reminds you to to take a selfie every day, and has an outline of a face to line
your own face up with on the screen, so that all of the photos line up with
each other. You can then turn the photos into a timelapse video of your face
changing through time.

I decided to do something a little different. I downloaded all of the images,
and then used a few lines of Python code to merge them all into a single,
average image. The result is amazing, especially given how different a lot of
the images were. It's recognisably me, but beautifully blurred out like an
impressionist painting.

![Average selfie](/assets/average-selfie.jpg)

Briefly, here's how the code works. It grabs the filenames of all of the JPGs
in the folder, opens them one by one, and then appends all of the RGB values of
each pixel in each image to a list. Then, it goes back through that list and
calculates the average RGB values for each pixel. Finally, it creates a new
image using those average RGB values for each pixel.

I adjusted the image very slightly in Photoshop, tweaking the curves a little,
and converting it to a landscape image with Photoshop's content-aware fill.

The code's below, so give it a go yourself! The images needn't be selfies,
they could be any group of similar photos, maybe images of landmarks grabbed
from Google Maps, or photos of a particular celebrity?

```python
import glob
from PIL import Image

images = glob.glob('*.jpg')
listofimages = [[] for x in range(len(images))]
i = 0

for image in images:
	im = Image.open(image)
	w, h = im.size
	for wpix in range(w):
		for hpix in range(h):
			r, g, b = im.getpixel((wpix, hpix))
			listofimages[i].append((r, g, b))
	i += 1

averageimage = []

for pixel in range(im.size[0] * im.size[1]):
	rvals = [image[pixel][0] for image in listofimages]
	r = sum(rvals) / len(rvals)
	gvals = [image[pixel][1] for image in listofimages]
	g = sum(gvals) / len(gvals)
	bvals = [image[pixel][2] for image in listofimages]
	b = sum(bvals) / len(bvals)
	averageimage.append((r, g, b))

newimage = Image.new('RGB', (im.size))

j = 0

for wpix in range(w):
	for hpix in range(h):
		newimage.putpixel((wpix, hpix), (averageimage[j]))
		j += 1

newimage.save('average.jpg', 'JPEG')
```
