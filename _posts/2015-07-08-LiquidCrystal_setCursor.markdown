---
layout: post
title:  "Function Help: LiquidCrystal::setCursor"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::setCursor


	void LiquidCrystal::setCursor(uint8_t row, uint8_t col);

This function puts the cursor at the specified position. The position is zero-based.
If one of the arguments is outside the bounds of the screen, it will cause undefined behavior (bad stuff).

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);

	//I want to write two X at the middle of the bottom row
	lcd.setCursor(7, 1);
	lcd.print("XX");


