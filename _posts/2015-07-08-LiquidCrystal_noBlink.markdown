---
layout: post
title:  "Function Help: LiquidCrystal::noBlink"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::noBlink


	void LiquidCrystal::noBlink();

This function makes the cursor stop blinking. It blinks by default.

Usage:
Adafruit_RGBLCDShield
	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);
	lcd.noBlink();


