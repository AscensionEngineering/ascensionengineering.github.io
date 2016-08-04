---
layout: post
title:  "Lab 9: Battery Tester"
date:   2015-07-19 13:15:30
categories: docs
---

We will be making something directly useful: a battery tester! Specifically, we will want to be able to measure remaining charge in a 1.5V alkaline battery, such as AA and AAA batteries.

![Alkaline State of Charge]({{site.url}}/images/Alkaline-SOC.jpg)  
(source: [Battery University](http://batteryuniversity.com/learn/article/examining_loading_characteristics_on_primary_and_secondary_batteries))

The voltage in an alkaline cell decreases (very roughly) in a linear fashion with regards to the remaining energy in the battery, which is useful for us. Many types of batteries have an extremely non-linear relationship between voltage and remaining energy. We will use this approximation for alkaline batteries: `Charge Remaining = 125 * ((Battery Voltage * 0.0049) - 0.8)`, where `Charge Remaining` is a percentage.  `Battery Voltage` will need to be multiplied by 0.0049 to be converted from an integer value from `A1` to actual volts, since 5 volts of input range divided by 1024 voltage steps ≈ 0.0049. These alkaline batteries have a nominal voltage of 1.5 volts, but they will often measure 1.6 volts when they are brand new, and they can be assumed totally dead at 0.8V. `1.6V - 0.8V = 0.8V` and `125 * 0.8 = 100%`, which is how the approximation was derived. A more accurate polynomial fit could surely be generated, if you'd like to make yours more accurate.

The diagram for this lab is remarkably simple, excluding the LCD shield:
![Lab 9 diagram]({{site.url}}/images/lab_9.jpg)

This lab will simply rely upon connecting any AA or AAA battery's positive terminal to the Arduino analog input of your choice and the negative terminal to the Arduino's ground, except for analog input 0, `A0`, because that one is used by the LCD shield. Use the LCD shield to display the charge percentage remaining.

(If you want to print special characters to the LCD, take a look [here](http://electronic-engineering.ch/microchip/datasheets/lcd/charset.gif).  You will need to convert the binary to decimal, and then the decimal value will need to be cast to a `char`.)
