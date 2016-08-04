---
layout: post
title:  "Function Help: delayMicroseconds"
date:   2015-07-08 15:37:30
categories: docs
---

	delayMicroseconds

	void delayMicroseconds(unsigned int time);

This function delays the program the slecified number of microseconds.
It works accuratley for times of 4us to about 16,000us.
If you want to delay for longer than a few thousand microseconds, use delay() instead.

Usage:

	//alternate pin 1 HIGH and LOW very fast
	//Imagine there's an LED linked to it, and it's blinking every second.
	digitalWrite(1, HIGH);
	delayMicroseconds(100);
	digitalWrite(1, LOW);
	delayMicroseconds(100);


