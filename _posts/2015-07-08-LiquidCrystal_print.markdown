---
layout: post
title:  "Function Help: LiquidCrystal::print"
date:   2015-07-08 15:37:30
categories: docs
---

	LiquidCrystal::print


	void LiquidCrystal::print(const String &str);					//prints C++ strings
	void LiquidCrystal::print(const char *cstr);					//prints C strings
	void LiquidCrystal::print(char c, int size = BYTE);				//prints a single character
	void LiquidCrystal::print(unsigned char uc, int size = BYTE);	//prints a single unsigned character
	void LiquidCrystal::print(int i, int base = DEC);				//prints an integer
	void LiquidCrystal::print(unsigned int ui, int base = DEC);		//prints an unsigned integer
	void LiquidCrystal::print(long li, int base = DEC);				//prints a long integer
	void LiquidCrystal::print(unsigned long uli, int base = DEC);	//prints an unsigned long intager
	void LiquidCrystal::print(double val, int digits = 2);			//prints a double, with a certain number of gigits past the decimal

These functions take something and print them to the LCD. 

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
	lcd.print(str);
	lcd.print(cstr);
	lcd.print(i);
	lcd.print(ui);
	lcd.print(li);
	lcd.print(uli);
	lcd.print(val, 0);

	//these will print the character
	lcd.print(c);
	lcd.print(uc);


