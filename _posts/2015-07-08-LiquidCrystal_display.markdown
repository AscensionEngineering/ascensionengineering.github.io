---
layout: post
title:  "Function Help: LiquidCrystal::display"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::display


	void LiquidCrystal::display()

This is the counterpart to noDisplay(). It turns the display back on. The display is on by default, so there is no need to call this at start, only after a call to noDisplay().

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);

	//some stuff that makes us want to turn the display off

	lcd.noDisplay();

	//do some stuff, wand LCD on again

	lcd.display();


