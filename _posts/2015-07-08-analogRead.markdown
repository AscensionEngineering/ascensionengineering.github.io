---
layout: post
title:  "Function Help: analogRead"
date:   2015-07-08 15:37:30
categories: others
---

	analogRead

	int analogRead(uint8_t pin);

This function reads the current voltage from an analoy pin, and returns 0 for 0v, 1024 for 5v, or somewhere inbetween for other voltages relative to the maximum.
There are five analog pins.
If you read a pin that is not connected to anything, the function will return nothing useful.

Usage:
	
	//I want to know Pin 2's value
	int pin2Value = analogRead(2);

	//this is about the voltage read (warning: floating point operatinos are slow!)
	float pin2Voltage = pin2Value / 1024.0;


