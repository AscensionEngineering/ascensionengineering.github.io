---
layout: post
title:  "Function Help: LiquidCrystal::autoscroll"
date:   2015-07-08 15:37:30
categories: others
---

	LiquidCrystal::autoscroll


	void LiquidCrystal::autoscroll();

This function will left justify text from the cursor.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);
	lcd.autoscroll();
	lcd.print("This is a large string I'd like to autoscroll.");


