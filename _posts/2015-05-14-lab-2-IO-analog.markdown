---
layout: post
title:  "Lab 2: I/O With Analog and Arithmetic"
date:   2015-05-14 14:35:30
categories: others
---
This lab will focus on changing the previous lab to use an analog input, and replacing one of the LEDs with a piezoelectric speaker.

The first LED from last lab is still connected to `pin 10`, but now instead of the second LED, let's use the piezoelectric speaker connected to `pin 9`, and instead of the button, let's use a potentiometer. Note that we no longer need a resistor connected to pin 5 because piezo elements don't form a short circuit when they're on. The potentiometer we're using is the leftmost one, which is connected to `A0`, analog input 0, rather than `pin 3`, and there are some other changes to the circuit there.

Background
==========

Potentiometers
--------------

Once the circuit is built, let's think about how the potentiometer works. One pin is accepting 5 volts from the Arduino, and the other is connecting back to ground. Between those two pins, there is 10 thousand ohms of resistance, or 10kΩ. The center pin is connected to the knob, which you can think about as moving a wire along that 10kΩ of resistance internally. The resistance between a chosen input pin (5v or ground) and the center pin can vary from nearly zero resistance all the way up to 10kΩ, depending on which way you turn it. As the resistance varies, the voltage on the center pin will vary as well, as more of the 5 volt input lingers on the variable resistance of the center pin.

Analog vs Digital
-----------------

What is analog? Analog is essentially the opposite of digital. So, let's talk about what digital really means. A digital signal is one that has a predefined number of "steps" in it. You could have a digital signal that has a value of 0 at 0 volts, a value of 1 at 4 volts, a value of 2 at 8 volts, and a value of 3 at 12 volts. Voltages between those would _round_ to the nearest value. Computers deal almost exclusively in digital signals with two steps. A voltage of 0 volts is represented by a 0, and a voltage of 5 volts is represented by a 1. The top of voltage varies from device to device. Cutting-edge electronics like an Intel Core i7 run on less than 1.2 volts, which means that the difference between a 1 and a 0 is also just 1.2 volts.

An analog signal is therefore a signal that _doesn't_ have steps. It is a _continuous_ signal, one with an infinite number of possible values. Even from 0 volts to 0.000001 volts, there are an infinite number of possible values for an analog signal. Since storing a number with infinite precision isn't very practical, microcontrollers like the Arduino can _read_ analog values as an approximation. Since 5 volts is the high voltage that the Arduino is powered with, that's the highest analog value it can read. The hardware in the Arduino that reads analog values is known as an _ADC_, an Analog to Digital Converter. The Arduino has a 10-bit ADC, so it represents the infinite values of the analog signal with 10-bits of digital steps, or 1,024 values from 0 to 1023. If the Arduino sees 5 volts on `A0`, it will read a value of 1023. If it sees a value of 2.5 volts, it will read a value of about 512.

The Lab
=======

Our goal is to make an LED and a piezo element blink and click, respectively, for 10ms at a varying interval. The functions we need for this lab are `pinMode`, `analogRead`, `digitalWrite`, and `delay`.

`delay` simply accepts an integer specifying how many milliseconds to wait. `delay(10)` will stop the code from running for 10 milliseconds. `analogRead` works just like `digitalRead` worked in the last lab, except it will return an `int`eger approximation instead of a boolean `true`/`false`. For example, `int value = analogRead(0);` will read the value from `A0` into `value`. You've already used `digitalWrite` and `pinMode`, but to recap, `digitalWrite` sets a pin to either 5 volts or 0 volts. `pinMode` will let you set a pin to be an `INPUT` or an `OUTPUT`. Pin `A0` is an analog input, so you won't set the `pinMode` on it. It _cannot_ be anything else, at least as far as we're concerned. There are advanced ways to re-use analog inputs, but don't worry about them here. Therefore, all you have to worry about is making the LED and Piezo into outputs.

**Useful tip:** `HIGH` is another way to write `1`, and `LOW` is another way to write `0` on the Arduino. Try to avoid `magic numbers` as much as possible, which are numbers that seem to come from nowhere. `digitalWrite(firstLED, HIGH)` is _much_ easier to understand than `digitalWrite(10, 1)`. Before the `void setup()` function, you can declare "global variables" simply by writing code like `int firstLED = 10;`. Try it! It will make your code better.

To do this lab, we want to `analogRead` the value of the potentiometer, turn on the LED and the Piezo, `delay` for 10ms, then turn off the LED and the Piezo. We then want to `delay` for however many milliseconds the value of the potentiometer was. If the potentiometer is about halfway, we'll be delaying for about 500ms, or half a second, for example.

Now, we want to compress the range of values. Having it wait a full second between blinking and clicking is boring! So, if you divide the analog value by 20, the longest the system will wait is one twentieth of a second, which is much better. Try it out, and notice how you have much finer control over the higher-speed clicking and blinking, and there is no way to slow it down too much. Let's try dividing by 80. Do that, and you'll notice that as you move the potentiometer back and forth, you just seem to be adjusting the brightness of the LED! This is related to a concept called _pulse width modulation_, but we won't talk about that today. Feel free to research it though!

The final step in this lab is to make it so that the LED is still visibly blinking, but we have our fine control over the speed. So, let's do the division by 40 this time and let's add 20 to the value after the division and run it.

**Troubleshooting Tips**

1. Make sure that the potentiometer is connected to `A0`! 
