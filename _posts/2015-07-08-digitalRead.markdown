---
layout: post
title:  "Function Help: digitalRead"
date:   2015-07-08 15:37:30
categories: docs
---

	digitalRead

	int digitalRead(uint8_t pin);

This function reads a value from a pin and returns it.
It will return either HIGH or LOW.

If a pin is not connected to anything, this function will return nothing useful.
If you read a pin that has not been set to INPUT, it will also not return anything useful.

Usage:

	//I want to know what pin 6 reads
	int pin6Value = digitalRead(6);


