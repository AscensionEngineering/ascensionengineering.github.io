---
layout: post
title:  "Function Help: LiquidCrystal::noCursor"
date:   2015-07-08 15:37:30
categories: others
---

	LiquidCrystal::noCursor


	void LiquidCrystal::noCursor();

This function turns display of the cursor off. The cursor is displayed by default.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);
	lcd.noCursor();


