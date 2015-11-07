---
published: false
title: Bernaccatron
layout: post
---
# Bernaccatron

## is a way not to get soaked

I commute to work by bicycle. While this is great, I often forget to look at the weather forecast, and so get swamped by rain and wish I had a car (well not really, driving in traffic kills me). So I need something that
tells me the what the weather is going to be like in the next hours or days, without me asking for it.

I have a PIR sensor, a WiPi fresh from the mail, ws2812 leds.. I should be sorted!

The idea is that every led shows temperature as color, and rain with a pulsating luminosity, the greater the chance of rain, the fastest the pulsation. So when I walk to the door the system wakes up, fetches the weather from some service, and then lights up 8 leds, one for each 6 hours period in the nect two days.

