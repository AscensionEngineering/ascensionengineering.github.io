---
layout: post
title:  "Keyword Help: while, do"
date:   2015-07-08 15:37:30
categories: docs
---

	while, do

These keywords are used for looping. The general syntax is:

	while (<expr>){

		//do this over and over again until <expr> is false

	}

	do {

		//do this once, then check <expr>, and keep doing until it is false

	} while (<expr>);

where <expr> is a boolean expression.

The first of the above is called a while loop. It will execute the statements between the {} until its condition is false.

The second loop is a do-while loop. It will ALWAYS execute the statements in the {} once, then check the expression, and behave as a while loop from there on out.

Usage:

	bool done = false;

	while (!done){

		//do something, eventually setting done to true

	}

	do {

		//done is currently true, so this will happen only once.

	} while (!done);
