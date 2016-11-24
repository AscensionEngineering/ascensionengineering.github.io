---
layout: post
title:  "Lab 10: Music Box"
date:   2015-07-19 13:10:30
categories: others
---

In this final structured lab, we will be making a small music box. We will simply be using the piezo element on pin 9 with some software for this lab.

We will need to create a struct, which will allow you to store both a frequency and duration into a single element of an array, since we will be using an array to represent the notes of a song.

    struct Note
    {
    	unsigned int frequency;
    	unsigned long duration;
    };

There is a built in function on Arduino called `tone` which allows you to output a square wave onto a digital pin, with a given frequency and duration. An example of tone would be `tone(9, 400, 500);` followed by `delay(500);`, which would generate a 400 Hz tone on pin 9 for 500 milliseconds. Another option is to create a `tone(pin, frequency)` and a `delay(duration)` right after. If you go with the second option, you will need to add `noTone(9);` at the end of your `setup` function to stop the piezo from buzzing annoyingly after the program ends.

For the purposes of this demo, we will have no code in the `loop` function, only place code in the `setup` function so things will happen only once. The reset button on the Arduino can act as a "play" button if the sequence needs to be heard again.

An array of the aforementioned structs could be constructed as `Note notes[3];`. The frequency element, for example, of the second note could be accessed as `notes[1].frequency`. You should use a for loop to loop over all of the notes and play their tone, rather than repeatedly copying and pasting code for each note, since that would be largely defeat the purpose of having an array in the first place.

Make sure the song is at least 10 notes long with at least 5 different notes, and demonstrate it to the TA.

## Be creative. Playing linearly increasing frequencies is just boring.

For some extra guidence on converting a note into frequency, follow this [link]({% post_url 2015-11-09-pitches %}).