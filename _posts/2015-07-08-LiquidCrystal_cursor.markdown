---
layout: post
title:  "Function Help: LiquidCrystal::cursor"
date:   2015-07-08 15:37:30
categories: others
---

	LiquidCrystal::cursor


	void LiquidCrystal::cursor();

This function enables display of the cursor. The cursor is displayed by default, so you only would need to call this after a call to noCursor();

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);

	//do something and want the cursor gone
	lcd.noCursor();

	//do something else and want it back on
	lcd.cursor();


