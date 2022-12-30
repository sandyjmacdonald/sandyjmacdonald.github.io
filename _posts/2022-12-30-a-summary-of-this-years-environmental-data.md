---
layout: post
title: A summary of this year's environmental data
date: 2022-12-30 19:20:00
summary: Summarising some tidbits of analysis of my home environmental data from this past year, in the medium of tweets.
tags: ["data analysis", "grafana", "influxbdb", "pimoroni", "raspberry pi"]
visible: 1
---

Looking back through [my tweets from the past year](https://twitter.com/sandyjmacdonald), I realised that I'd actually tweeted some interesting tidbits of analysis of the environmental data that I've collected, so I thought I'd put together a mish-mash of the best bits...

## Tonga volcanic eruption

On January 15th this year, the [Hunga Tonga–Hunga Haʻapai volcano in the Tongan archipelago erupted](https://en.wikipedia.org/wiki/2022_Hunga_Tonga%E2%80%93Hunga_Ha%CA%BBapai_eruption_and_tsunami). It is now known that this was the most powerful atmospheric explosion recorded in modern times, and probably second only to the eruption of Krakatoa in 1883.

Although my weather station and other Raspberry Pi-related sensors measure atmospheric pressure, they do so only every 5 minutes. Reading on Twitter about some people recording a pressure wave passing on their weather stations, I hastily set up a Raspberry Pi with a BME280 sensor to measure the pressure wave with greater resolution.

14 hours and 20 minutes after the eruption, I was able to record the wave passing over York, more than 16,000 km away, and travelling at just less than the speed of sound.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">The Tonga volcanic eruption pressure shockwave measured on a hastily set up <a href="https://twitter.com/pimoroni?ref_src=twsrc%5Etfw">@pimoroni</a> BME280 sensor and <a href="https://twitter.com/Raspberry_Pi?ref_src=twsrc%5Etfw">@Raspberry_Pi</a> in York, UK. That&#39;s 16,270 km away, and taking 14h 20m to get here gives a speed of 1,135 km/h or 315 m/s!<a href="https://twitter.com/hashtag/Tonga?src=hash&amp;ref_src=twsrc%5Etfw">#Tonga</a> <a href="https://twitter.com/hashtag/TongaVolcano?src=hash&amp;ref_src=twsrc%5Etfw">#TongaVolcano</a> <a href="https://t.co/b4JzUtdih9">pic.twitter.com/b4JzUtdih9</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1482446483655962626?ref_src=twsrc%5Etfw">January 15, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

In the end, I managed to capture the atmospheric pressure wave making *three* full trips around the globe in either direction (since the wave is like dropping a pebble onto a pond, with a circular ripple moving outwards in all directions).

<blockquote class="twitter-tweet" data-conversation="none"><p lang="en" dir="ltr">Well, well, well... I spoke too soon. Thought I&#39;d check the data one last time, and the pressure wave from the Tonga eruption has made THREE full trips round the globe now!!! 😲 ~100,000 km travelled and a remarkably consistent speed of 311m/s +/-2.5. <a href="https://twitter.com/hashtag/Tonga?src=hash&amp;ref_src=twsrc%5Etfw">#Tonga</a> <a href="https://twitter.com/hashtag/TongaEruption?src=hash&amp;ref_src=twsrc%5Etfw">#TongaEruption</a> <a href="https://t.co/PJQJYzJEeg">pic.twitter.com/PJQJYzJEeg</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1483749685902856200?ref_src=twsrc%5Etfw">January 19, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Clearing the air

In February, storm Eunice hit the UK, and I spotted on my Grafana dashboard that, after the heavy rainfall from the storm, there was a clear and obvious drop in the particulate matter sensor readings recorded by my Pimoroni Enviro+ board and Raspberry Pi.

This is because the rain literally washes the particulates out of the air. So the old saying about a storm clearing the air really is true! I spotted the same phenomenon several more times through the year.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">When people talk about rain clearing the air, it&#39;s literally true! Data here from my <a href="https://twitter.com/pimoroni?ref_src=twsrc%5Etfw">@pimoroni</a> weather station and particulate matter sensor showing that the <a href="https://twitter.com/hashtag/StormEunice?src=hash&amp;ref_src=twsrc%5Etfw">#StormEunice</a> rainfall overnight coincides with a sudden drop in particulates (air pollution nasties). <a href="https://twitter.com/hashtag/grafana?src=hash&amp;ref_src=twsrc%5Etfw">#grafana</a> <a href="https://twitter.com/hashtag/influxdb?src=hash&amp;ref_src=twsrc%5Etfw">#influxdb</a> <a href="https://t.co/nrTio5LSWO">pic.twitter.com/nrTio5LSWO</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1494589445407977506?ref_src=twsrc%5Etfw">February 18, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

This period of a few days actually ended up being [one of the wettest spells of the whole year](/2022/12/30/analysing-a-year-of-rainfall-data/).

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Sheesh! A day and a half of pretty much solid rain. <a href="https://t.co/N6zGSbaKXB">pic.twitter.com/N6zGSbaKXB</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1495504924439896066?ref_src=twsrc%5Etfw">February 20, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I went out and took some pretty photos of the River Ouse flooding a couple of days later. There were predictions that the Ouse could reach its highest ever level but fortunately that didn't prove to be the case.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">This is how the River Ouse in York was looking at lunchtime today. Pretty high and still rising... <a href="https://twitter.com/bbcweather?ref_src=twsrc%5Etfw">@bbcweather</a> <a href="https://twitter.com/BBCLookNorth?ref_src=twsrc%5Etfw">@bbclooknorth</a> <a href="https://twitter.com/yorkpress?ref_src=twsrc%5Etfw">@yorkpress</a> <a href="https://twitter.com/theyorkmix?ref_src=twsrc%5Etfw">@theyorkmix</a> <a href="https://twitter.com/hashtag/york?src=hash&amp;ref_src=twsrc%5Etfw">#york</a> <a href="https://twitter.com/hashtag/ouse?src=hash&amp;ref_src=twsrc%5Etfw">#ouse</a> <a href="https://twitter.com/hashtag/flood?src=hash&amp;ref_src=twsrc%5Etfw">#flood</a> <a href="https://twitter.com/hashtag/stormfranklin?src=hash&amp;ref_src=twsrc%5Etfw">#stormfranklin</a> <a href="https://t.co/qDuUliZu4U">pic.twitter.com/qDuUliZu4U</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1495799527634317319?ref_src=twsrc%5Etfw">February 21, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## NOx gases and sunlight

I'm still not sure what this is all about, but I spotted a few times that on bright, sunny days with high pressure, the readings from the NOx gas sensor on my Enviro+ board shot up a few hours later. Usually this lag is about 7 hours.

Any ideas what could cause this? [Let me know!](https://twitter.com/sandyjmacdonald)

<blockquote class="twitter-tweet" data-conversation="none"><p lang="en" dir="ltr">On bright, warm days, usually during a period of high pressure, the NOx readings spike and show a very similar pattern to the light level, except with a lag of about 7 and a bit hours.<br><br>The past couple of days have been a perfect example of it.<br><br>2/3 <a href="https://t.co/ERiaLSCvNU">pic.twitter.com/ERiaLSCvNU</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1507484828299579394?ref_src=twsrc%5Etfw">March 25, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Wind data analysis

At the end of June, I'd had my weather station recording data for a year, so I did some analysis of the wind speed data that I'd recorded.

The wind speed, averaged out across the 12 months of data, shows a definite trend towards being windiest around the middle of the day:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Now that I&#39;ve got a year&#39;s worth of data from my <a href="https://twitter.com/pimoroni?ref_src=twsrc%5Etfw">@pimoroni</a> / <a href="https://twitter.com/Raspberry_Pi?ref_src=twsrc%5Etfw">@Raspberry_Pi</a> weather station, I thought I&#39;d do some analysis of the wind speed data. 🍃<br><br>Turns out that the wind speed shows a definite trend through the day: less windy at night, windiest at about 13:30.<br><br>1/2 <a href="https://t.co/nnFp5J4kNl">pic.twitter.com/nnFp5J4kNl</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1541077987273150467?ref_src=twsrc%5Etfw">June 26, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

The rough trend was that the spring and autumn months were the windiest, and the summer months were more calm:

<blockquote class="twitter-tweet" data-conversation="none"><p lang="en" dir="ltr">The trend holds up for most months too, and looks like Feb/Mar/Apr and Oct are the windiest months, so spring and autumn, basically. Summer not so windy. <a href="https://twitter.com/hashtag/dataviz?src=hash&amp;ref_src=twsrc%5Etfw">#dataviz</a> <a href="https://twitter.com/hashtag/rstats?src=hash&amp;ref_src=twsrc%5Etfw">#rstats</a> <a href="https://twitter.com/hashtag/ggplot?src=hash&amp;ref_src=twsrc%5Etfw">#ggplot</a> <a href="https://twitter.com/hashtag/tidyverse?src=hash&amp;ref_src=twsrc%5Etfw">#tidyverse</a> <br><br>2/2 <a href="https://t.co/3jNDoJRQns">pic.twitter.com/3jNDoJRQns</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1541078021871894530?ref_src=twsrc%5Etfw">June 26, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## June heatwave

In June, we had a heatwave where temperatures were forecast to hit 40°C in the UK. In the end, the temperatures I recorded on my weather station *only* made it to just over 36°C, but indoor temperatures weren't far off outdoor temperatures. Horrid.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Outdoor temperature today just edged out yesterday, but the extra day&#39;s heat has made it significantly hotter in the house. It&#39;s horrid. <a href="https://twitter.com/hashtag/ukheatwave?src=hash&amp;ref_src=twsrc%5Etfw">#ukheatwave</a> <a href="https://t.co/mTz1TNcicU">pic.twitter.com/mTz1TNcicU</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1549439105582374912?ref_src=twsrc%5Etfw">July 19, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Smooooooth light levels

In the middle of August, we had a spell of very high pressure and, as a result, completely cloudless skies. After a few days, I spotted on my Grafana dashboard that the plots of the light level were incredibly smooth, almost like I'd mathematically smoothed the data out, and successive days were almost carbon-copies of each other.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Incredibly consistent, smooth light levels from my weather station over the past few days. Compare to the same period last week in the second picture. <a href="https://t.co/AsMVZVigRD">pic.twitter.com/AsMVZVigRD</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1558363783789150209?ref_src=twsrc%5Etfw">August 13, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

This was a good opportunity to plot the light level and air temperature together. The resulting plot showed that the sun starts heating the air quickly, but the air temperature takes a little longer to peak than does the light level.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Plotting light level against temp. for yesterday, you can see that the sun starts heating the air up quickly but the temp. takes a little longer to peak. The light level tails off earlier than expected because the weather station is at the east-facing side of the house. <a href="https://t.co/aFe3wsw9dd">pic.twitter.com/aFe3wsw9dd</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1558387808439508997?ref_src=twsrc%5Etfw">August 13, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Bonfire night

Ah, the annual tradition of setting off explosives and spewing huge amounts of pollutants into the air in the name of... er... celebrating us stopping someone setting off explosives 417 years ago. Yeah, I don't get it.

In the screenshot from my Grafana dashboard below, you can see the particulate matter levels rise stratospherically on Bonfire Night. The blue and red lines are the WHO recommended limits for PM2.5 and PM10, 10 and 20 µg/m³, respectively. You can see the levels reached around 200 µg/m³!

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Yeesh! <a href="https://t.co/JnHxPcutjT">pic.twitter.com/JnHxPcutjT</a></p>&mdash; Sandy Macdonald (@sandyjmacdonald) <a href="https://twitter.com/sandyjmacdonald/status/1589023917259341824?ref_src=twsrc%5Etfw">November 5, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>