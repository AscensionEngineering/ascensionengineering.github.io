---
layout: post
title:  "Function Help: digitalWrite"
date:   2015-07-08 15:37:30
categories: docs
---

	digitalWrite

	void digitalWrite(uint8_t pin, uint8_t value);

This function writes a value (HIGH or LOW) to a pin.

If you use this with a pin that is not set to output, it may not actually be set to the value requested.
Do not use this with an input pin.

Usage:

	//I need to set pin 9 to HIGH
	digitalWrite(9, HIGH);


