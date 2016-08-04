---
layout: post
title:  "Function Help: LiquidCrystal::println"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::println


	void LiquidCrystal::println(const String &str);					//prints a C++ string and a newline
	void LiquidCrystal::println(const char *cstr);					//prints a C string and a newline
	void LiquidCrystal::println(char c, int size = BYTE);			//prints a single character and a newline
	void LiquidCrystal::println(unsigned char uc, int size = BYTE);	//prints a single unsigned character and a newline
	void LiquidCrystal::println(int i, int base = DEC);				//prints an integer and a newline
	void LiquidCrystal::println(unsigned int ui, int base = DEC);	//prints an unsigned integet and a newline
	void LiquidCrystal::println(long li, int base = DEC);			//prints a long integer and a newline
	void LiquidCrystal::println(unsigned long uli, int base = DEC);	//prints an unsigned long integer and a newline
	void LiquidCrystal::println(double val, int digits= 2);			//prints a decimal value and a newline
	void LiquidCrystal::println();									//prints just a newline

These functions work just the same as the print functions, just that they also print a newline character after everything.

This function is what we call "overloaded." There are multiple definitions for the same named function that take different arguments. Overloads are generally provided for convinence; these are provided so you don't have to convert every primitave variable to a string before printing. The overloaded functions do that for you.
This function also has a few default arguments for certain overloads of it. For now, you can ignore all of them excpet for the very last one. It tells it how many digits past the decimal place to print.

Usage:

	LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
	lcd.begin(16, 2);

	String str = "12";
	char * cstr = "12";

	char c = 'c'
	unsigned char uc = 'u'

	int i = 12;
	unsigned int ui = 12;
	long int li = 12;
	unsigned long uli = 12;
	double val = 12.012345;

	//each one of these will print a 12
	lcd.println(str);
	lcd.println(cstr);
	lcd.println(i);
	lcd.println(ui);
	lcd.println(li);
	lcd.println(uli);
	lcd.println(val, 0);

	//these will print the character
	lcd.println(c);
	lcd.println(uc);


