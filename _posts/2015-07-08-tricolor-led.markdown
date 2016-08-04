---
layout: post
title:  "Hardware Help: Tricolor LED"
date:   2015-07-08 15:37:30
categories: others
---

	Tricolor LED

The tricolor LED is a composite device. It actually has three LEDs inside of it, and all of their anodes (positive ends) are connected together and come out as a single pin. It has four pins, three of which are cathodes (negative ends), and one of which is the common anode. The longest pin is the common anode, which means that it will be connected to 5 volts. The lone pin beside it is the red cathode, the pin on the other side is blue, and the pin farther away is green. Each cathode should be connected to a 560 ohm resistor, and then the output of that resistor connected to a pin on the Arduino. When the output on that pin is HIGH, there is no voltage difference between the input and the output, so the LED will be off. When the output is LOW, electricity can drain through the LED into the pin on the Arduino. So, by default, you should keep the LED pins for the tri-color HIGH, and then turn each one LOW whenever you want to turn it on.