---
layout: post
title:  "Function Help: analogWrite"
date:   2015-07-08 15:37:30
categories: others
---

	analogWrite

	void analogWrite(uint8_t pin, int value);

This function uses a digital pin to simulate analog output. It will Continue this until you call analogWrite() again, or a digitalRead() or digitalWrite on the same pin.
It takes in a pin number to use, and what is refered to as the duty cycle as value, between 0 and 255.
A value of 0 is always off, and 255 is always on.
This function works with pins 3, 5, 6, 9, 10, 11. The max fewquency for them is 490Hz, except for pins 5 and 6; they are at 980Hz.
You do not need to set a pin to either INPUT or OUTPUT to use this function.

USAGE:

	//I have an LED on pin 9, and a potentiometer on analog pin 3
	//I want to flash the LED at varying speeds as you adjust the potentiometer
	int value = analogRead(3);	//value is somewhere between 0 and 1024
	analogWrite(8, value / 4);	//I need it to be between 0 and 255


