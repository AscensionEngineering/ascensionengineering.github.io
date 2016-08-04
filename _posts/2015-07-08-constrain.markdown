---
layout: post
title:  "Function Help: constrain"
date:   2015-07-08 15:37:30
categories: others
---

	constrain

	#define constrain(amt,low,high) ((amt)<(low)?(low):((amt)>(high)?(high):(amt)))

This macro constrains a number bewtween a min and max value.
It returns the value if it is between low and high, high if value is greater, and low it it is lower.

Usage:
	
	const int MAX = 20;
	const int MIN = 12;
	
	int a = 15;
	int b = 5;
	int c = 32;

	int d = constrain(a, MIN, MAX);	//d is a, because a was between the values
	int e = constrain(b, MIN, MAX);	//e is MIN, because b was less than MIN
	int f = constrain(c, MIN, MAX);	//f is MAX, becuase c was greater than MAX


