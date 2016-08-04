---
layout: post
title:  "Function Help: LiquidCrystal::scrollDisplayLeft"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::scrollDisplayLeft


	void LiquidCrystal::scrollDisplayLeft();

This function is used to scroll the display left to see text that does not fit on one entire line.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);
	lcd.print("This is a big string."); //this is too large to display on one line

	for (int i = 0; i < 6; ++i){

		lcd.scrollDisplayLeft();	//move display left
		delayMicroseconds(10000);	//wait so humans can see it (1 second);

	}


