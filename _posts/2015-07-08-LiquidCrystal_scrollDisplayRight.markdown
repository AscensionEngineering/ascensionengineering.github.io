---
layout: post
title:  "Function Help: LiquidCrystal::scrollDisplayRight"
date:   2015-07-08 15:37:30
categories: others
---

	LiquidCrystal::scrollDisplayRight


	void LiquidCrystal::scrollDisplayRight();

This function scrolls the display to the right.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);
	lcd.print("This is a big string."); //this is too large to display on one line

	for (int i = 0; i < 6; ++i){

		lcd.scrollDisplayLeft();	//move display left
		delayMicroseconds(10000);	//wait so humans can see it (1 second);

	}

	//now we want to move the display back
	for (int i = 0; i < 6; ++i){

		lcd.scrollDisplayRight();	//move display right
		delayMicroseconds(10000);	//wait so humans can see it (1 second);

	}


