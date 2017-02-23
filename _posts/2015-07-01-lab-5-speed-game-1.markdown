---
layout: post
title:  "Lab 5: Speed Game (Part 1)"
date:   2015-07-01 13:22:30
categories: others
---

It's time for a fun lab! For this lab, we’re going to use two buttons, the piezo speaker, and several LEDs!

The goal of this lab is to build a speed game. The gameplay should be as follows:

- simultaneously blink the LED on `pin 7` and click the piezo buzzer 3 times delaying for 333 milliseconds in
between to signify the game is about to start
- wait for a random amount of time (no more than 10 seconds)
- light up the LED on `pin 7` (indefinitely until someone presses their button)
- immediately begin buzzing the buzzer continuously for about 100 milliseconds (turning it on and off rapidly)
- whenever a user presses their button after this point, the LED on `pin 7` turns off and the buzzer sounds for another 100 milliseconds to signify the game is over. The LED corresponding to the user turns on to let them know that they were the winner.
- wait 4 seconds, then start over

To complete this lab you only need 1 new piece of information you do not already have, the random
function.

Random is defined roughly as random([long min], long max), which returns a randomly generated
number between the min and max values. The brackets indicating that the min parameter is optional, if
you only provide one argument it will be treated as the maximum.

`pin 10` and `pin 6` are for Player 1, `pin 3` and `pin 12` are for Player 2.

Good luck!
