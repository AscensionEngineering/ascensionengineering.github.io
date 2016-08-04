---
layout: post
title:  "Function Help: LiquidCrystal::home"
date:   2015-07-08 15:37:30
categories: others
---

	LiquidCrystal::home


	void LiquidCrystal::home();

This function sets the LCD's cursor to (0,0) (the top-left corner of the display)

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);
	lcd.print("lkjahdfs"); //junk we want to overwrite
	lcd.home();
	lcd.print("Better text!");


