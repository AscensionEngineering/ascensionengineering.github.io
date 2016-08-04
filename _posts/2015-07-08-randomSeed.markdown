---
layout: post
title:  "Function Help: randomSeed"
date:   2015-07-08 15:37:30
categories: docs
---

	randomSeed

	void randomSeed(unsigned long seed);

This function seeds the random number generator with a given seed.
It can be called without an argument to use a random seed.
If the random number generator is seeded with the same seed, it will produce the same set of random numbers each time.
You should call this function in setup() if you need random numnbers in the prograrm.

Usage:

	void setup(){

		//other setup code...
		randomSeed();

	}


