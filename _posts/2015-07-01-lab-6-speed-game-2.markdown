---
layout: post
title:  "Lab 6: Speed Game (Part 2)"
date:   2015-07-01 14:44:30
categories: others
---

It's time for another fun lab! For this lab, we're simply going to use the Apollo's display.

The goal of this lab is to build the speed game another way. The gameplay should be as follows:

- set the LCD to show some message indicating the players should wait before pushing a button.
- wait for a random amount of time (no more than 10 seconds)
- set the LCD to show an exciting message to get users to push the button (like "GO!")
- when one user presses their button after this point, the LCD should show a message indicating both that the game is over and who won.
- wait 2 seconds, then start it all over.

If you don't remember how to write to the LCD, feel free to [review the first tutorial]({% post_url 2015-05-11-getting-started %}).

To clear the LCD screen, simply write `lcd.clear()`. Writing `lcd.setCursor(0, 0)` will let you move the cursor back to the top left of the display, and this should also automatically happen when you use `lcd.clear()`.

To read the buttons, copy and paste the following code at the top of your file:

    enum Keycodes : int
    {
        btnUP,
        btnDOWN,
        btnLEFT,
        btnRIGHT,
        btnSELECT,
        btnNONE
    };
    
    int read_all_buttons()
    {  
        if (digitalRead(3))  return btnRIGHT;  
        if (digitalRead(5))  return btnUP; 
        if (digitalRead(4))  return btnDOWN; 
        if (digitalRead(6))  return btnLEFT; 
        if (digitalRead(2))  return btnSELECT;  
        return btnNONE;
    }

then in your code you can use this function by using code similar to the following:

    int button = read_all_buttons();
    if (button == btnUP)
    {
        //do something for the up button being pushed
    }
    
and `button` will now have the keycode for the button that was pushed.

`btnUP` represents the up button, but other options include `btnDOWN`, `btnLEFT`, `btnRIGHT`, and `btnSELECT`.

I recommend using `btnLEFT` and `btnRIGHT` for the two user buttons, but you can use whichever ones seem most appropriate.

Good luck!
