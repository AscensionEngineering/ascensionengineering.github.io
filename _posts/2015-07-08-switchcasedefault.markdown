---
layout: post
title:  "Keyword Help: switch, case, default"
date:   2015-07-08 15:37:30
categories: others
---

	switch, case, default

This is an alternate, simpler form of conditional. It is used to check a variable against a a set of fixed values.
A switch statement does what we call "falling-through". If not broken out of with break, it will execute every statement from the first true one downwards.
Switch statements can also ahve a default clause, which will only happen if no other conditions are true, or if it is fallen through to.

Usage:

	int x = 4;
	int y = 3;
	int z = 8;

	switch (x){

		case 0: { 
			//do something if x is 0
			y = 2*z;
			break; //but jump out of the switch, we don't want to go to "case 1."
		} case 1:{
			y = x + 2;
			//do something if x is 1 OR 2, since we have no break statement to keep it from continuing on into case 2.
			//this is *not* recommended.
		} case 2:{
			z = x * y;
			break;
		} default:{
			z = 25;
			break;
		}
	}

In this sample program, if x is zero, we just set y equal to double the value of z. If the value of x is 1, then we set y equal to x + 2, which is going to be 3, naturally, and then we continue on to set z equal to x * y. If the value of x is 2, then we *just* set z to x * y, we don't mess with the value of y, and if the value of x is anything else, we set z equal to 25.
