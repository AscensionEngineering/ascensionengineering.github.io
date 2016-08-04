---
layout: post
title:  "Function Help: LiquidCrystal::clear"
date:   2015-07-08 15:37:30
categories: others
---

	LiquidCrystal::clear


	void LiquidCrystal::clear();

This function clears the display, and sets the display's cursor to (0,0) (the top-left corner of the display)

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);
	lcd.print("lkjahdfs"); //junk we want off the screen
	lcd.clear();


