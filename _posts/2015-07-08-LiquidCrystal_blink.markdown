---
layout: post
title:  "Function Help: LiquidCrystal::blink"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::blink


	void LiquidCrystal::blink();

This function enables cursor blinking. The cursor blinks by default, so you only need to use it to reenable blinking after disabling it.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);

	//some stuff that makes us want to turn blinking off

	lcd.noBlink();

	//do some stuff, want blinking on

	lcd.blink();


