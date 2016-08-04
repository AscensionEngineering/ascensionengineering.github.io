---
layout: post
title:  "Function Help: LiquidCrystal::begin"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::begin


	void LiquidCrystal::begin(uint8_t cols, uint8_t rows, uint8_t charsize = LCD_5x8DOTS);

This function tells the object how large our LCD is, and what size characters it uses. We MUST call this function immediatley after creating an object, otherwise we'll have a bad time.
The third argument is optional; it has a default value that it will take if you do not pass one. 
Our LCD is 16x2, so you should always pass those numbers in. Our LCD also uses the default character size, so don't bother with the last argument.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16,2);


