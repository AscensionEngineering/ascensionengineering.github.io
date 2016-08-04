---
layout: post
title:  "Lab 5: Speed Game (Part 1)"
date:   2015-07-01 13:22:30
categories: others
---

It's time for a fun lab! For this lab, we're going to need two buttons, two normal LEDs, and the big tri-color LED.

The goal of this lab is to build a speed game. The gameplay should be as follows:

- set the tri-color LED to red
- wait for a random amount of time (no more than 10 seconds)
- set the tri-color LED to green
- whenever a user presses their button after this point, the tri-color LED changes to blue to signify the game is over, and the LED in front of that user turns on to let them know that they were the winner.
- wait 2 seconds, then reset the tri-color to red and start over

There are only two pieces of information you need to complete this lab that you don't already have: `random` and how to use the tri-color LED.

`random` is defined roughly as `long random([long min], long max)`. The brackets indiciating that the `min` parameter is optional, if you only provide one argument it will be treated as the maximum.

The tri-color LED is really just 3 LEDs in one package. There is nothing special about it. It has four pins, three of which are cathodes, and one of which is the common anode. The longest pin is the common anode, which means that it will be connected to 5 volts. The lone pin beside it is the red cathode, the pin on the other side is green, and the pin farther away is blue. Each cathode should be connected to a 560 ohm resistor, and then the output of that resistor connected to a pin on the Arduino. When the output on that pin is HIGH, there is no voltage difference between the input and the output, so the LED will be off. When the output is LOW, electricity can drain through the LED into the pin on the Arduino. So, by default, you should keep the LED pins for the tri-color HIGH, and then turn each one LOW whenever you want to turn it on.

This is the circuit layout for this week:
![Lab 5 diagram]({{site.url}}/images/lab_5.jpg)

Connect one button each to `pin 2` and `pin 3`. Connect one 560 ohm resistor in series with one LED to `pin 4`. Repeat for `pin 5`. Repeat that procedure for each cathode of the tri-color LED, connecting to `pins 6 through 8`. Connect the anode to `5V`. `pin 2` and `pin 4` are for Player 1, and `pin 3` and `pin 5` are for Player 2.

Good luck!
