---
layout: post
title:  "Function Help: LiquidCrystal::noAutoscroll"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::noAutoscroll


	void LiquidCrystal::noAutoscroll();

This function will right justify text from the cursor.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);
	lcd.noAutoscroll();
	lcd.print("This is a large string I'd like to autoscroll.");


