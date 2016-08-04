---
layout: post
title:  "Function Help: analogReference"
date:   2015-07-08 15:37:30
categories: docs
---

	analogReference

	void analogReference(uint8_t value);

This function sets the reference voltage for an analog pin, or the top voltage you expect to read from it.
You have two options:

	DEFAULT:	The default value for the board is used (5v)
	EXTERNAL:	The current voltage applied to the AREF pin is used (0v - 5v ONLY)

Usage:

	//I want my analog reverence to be 3v, and it is being applied to the AREF pin
	analogReference(EXTERNAL);

	//some time passes
	//now I want to use the default value again
	analogReference(DEFAULT);


