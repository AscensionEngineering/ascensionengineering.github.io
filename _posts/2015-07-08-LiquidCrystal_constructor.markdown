---
layout: post
title:  "Function Help: LiquidCrystal constructor"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal constructor


	LiquidCrystal(uint8_t rs, uint8_t enable, uint8_t d0, uint8_t d1, uint8_t d2, uint8_t d3);

This is the constructor for the LCD object; it creates a new one an initalizes it. You shoudl only ever make one of these.
For our shield, you'll always want to call it with the following arguments. They are the pin assignments for the shield.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);


