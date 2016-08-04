---
layout: post
title:  "Hardware Help: Temperature Sensor"
date:   2015-07-08 15:37:30
categories: others
---

	Temperature Sensor

The temperature sensor we use in this lab is the venerable TMP36. First announced around February 1st of 2001 by Analog Devices, this is an extremely easy to use, reliable, and inexpensive temperature sensor! Since there are no digital components to it at all, it outputs an analog value representing the current temperature.

The formula that governs this converison is straight forward: `Temp in °C = [(Vout in mV) - 500] / 10` ([source](https://learn.adafruit.com/tmp36-temperature-sensor)).