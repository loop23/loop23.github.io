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

So I began playing with the WiPy to see if I could get it to do what I wanted. Unfortunately the guys are in the mid of a API change thing, and all docs online refer to the old one. In case you are in my same situation, bear in mind that pyb and wipy are no more (there’s machine) and that delay is now in the time module. Please see the [latest API](http://micropython.org/resources/docs/en/latest/wipy/index.html).
So after some struggles I came up with

    import machine
    import time
    sensor = Pin(‘GP10’, Pin.IN, pull=Pin.PULL_UP)
    prev_val = -1
    while True:
        curr_val = sensor.value()
        if curr_val != prev_val: 
            print(‘Value is:’, curr_val)
            prev_val = curr_val
        time.sleep_ms(250)

Which is a bit noisy but is a good start - At least I know the sensor is working