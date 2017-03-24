---
layout: post
title:  "Lab 8: Lockbox"
date:   2015-07-19 13:05:30
categories: others
---

For this lab, we want to design a simple safe, which will use the display, some buttons, the piezo, and an LED. 

The end result should be that the display starts out showing "UNLOCKED" on the screen, with the LED on pin 10 turned on and the LED on pin 11 turned off, since this is a dangerous state to be in -- anyone could take our stuff! When the user presses "SELECT" it will lock the safe, which involves printing "LOCKED" on the screen, as well as turning on the "locked" LED and turning off the "unlocked" one. The next time SELECT is pressed, it will ask for a 4-digit code to be entered. If the code is correct, it will return to the unlocked state. If the code is wrong, it will print a message on the screen saying

          STOP!
     HACKER DETECTED

and then begin flashing the LED on 10 quickly and running the piezoelectric buzzer. The LED on 11 should stay on to indicate that the items in the lockbox are still safe. After about 5 seconds, it should stop and return to the locked state, ready for someone to try to unlock it again.

To do this, you will want to use an array to store the button sequence. To do this, simply initialize an array like so:

    int passwd[] = { btnUP, btnLEFT, btnLEFT, btnUP };

or whatever sequence you would like. In order to check the password the user enters against it, we will need an array to hold their attempt (that way they don't know which button push was wrong).

    int attempt[4];

Then we just need a for loop

    for (int i = 0; i < 4; i++)
    {
    	//store values into the attempt array here
    }

followed by another one that will check the values:

    for (int i = 0; i < 4; i++)
    {
    	//check each value in 'attempt' against the
    	//password array that was passed into this function
    }

if one of the values doesn't match up, then we should `break` out of the loop and start the 5-second error sequence before returning to the locked state.

(NOTE: Make sure that you have a comment at the top of your lab containing your password combination.)

This week, we are providing a code template for you, since this lab is a little complex:

    //THE PASSWORD IS: <tell us the key sequence here>

    /* !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
    *  DO NOT MODIFY OR ADD ANY CODE BELOW 
    *  THIS LINE UNTIL NEXT STATEMENT IN 
    *             CAPITAL TEXT
    *  !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
    */
    #include <LiquidCrystalShift.h>
    LiquidCrystalShift lcd(7, 8, A3);

    int unlockedLED = 10;
    int lockedLED = 11;
    int piezo = 9;

    enum Keycodes : int
    {
        btnUP,
        btnDOWN,
        btnLEFT,
        btnRIGHT,
        btnSELECT,
        btnNONE,
        btnANY
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

    //This function will return the key code that was
    //pressed. This is particularly useful if you ask
    //it to wait for btnANY, since you want to know
    //which key was pressed.
    int waitForKey(int keyCode)
    {
        //loop until the desired key has been pressed,
        //or if the developer just wants any button to be pressed,
        //wait on a button to be pressed.
        int pressedKey;
        do {
          pressedKey = read_all_buttons();
          delay(10);
        } while (pressedKey != keyCode && (pressedKey == btnNONE || keyCode != btnANY));
        
        //wait on the button to be released
        while (read_all_buttons() == pressedKey)
          delay(10);
        
        return pressedKey;
    }


    void setup() {
      pinMode(unlockedLED, OUTPUT);
      pinMode(lockedLED, OUTPUT);
      pinMode(piezo, OUTPUT);
      lcd.begin(16, 2); //it is a 16 x 2 character display
      // put your setup code here, to run once:

    }

    void loop() {
      // call the unlock function repeatedly, every time
      // we are ready to return to the unlocked state.
      unlock(); 
    }


    /* !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
     * DO NOT MODIFY OR ADD ANY CODE ABOVE THIS LINE.
     * !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
     */

    bool getPassword(int correctPassword[]) {
      /* You must implement the getPassword function.
       *
       * This function will listen for the user's
       * key presses and compare them to the password
       * stored in correctPassword. It should provide
       * visual feedback on the LCD in the form of a
       * single asterisk/star "*" character on the
       * second line of the LCD each time the user
       * presses a button. Even if they get the
       * password wrong, you still need to listen
       * to all of their keypresses. This way they
       * don't know which key was wrong.
       * 
       * Once the password entry is complete, you should
       * return either true or false depending on if the
       * user typed the password in correctly. This way
       * the function that called getPassword will be
       * able to take decisive action.
       */
    }

    /* This is the unlock function, it provides an example
     * of what these functions are supposed to look like.
     * This should not need to be modified.
     */
    void unlock() {
      lcd.clear();
      lcd.print("UNLOCKED");
      digitalWrite(unlockedLED, HIGH);
      digitalWrite(lockedLED, LOW);
      waitForKey(btnSELECT);
      lock();
    }

    void lock() {
      /* You must implement the lock function.
       *
       * This function will put the lockbox into
       * a locked state, as described in the lab.
       * This function should wait for the select
       * key to be pressed before calling into
       * the unlockAttempt state.
       */
    }

    void unlockAttempt() {
      /* You must implement the unlockAttempt function
       *
       * This function will print to the screen and
       * ask the user to input the password. It will
       * then call the getPassword function, which
       * will actually wait for each button press
       * and compare them to what is provided in the
       * "correctPassword" argument, which will be the
       * password that you have chosen. Depending on
       * whether getPassword returns true or false,
       * you will then move into either the unlockFailure
       * state, or you will move into the unlocked state.
       * 
       * If you want to move into the unlocked state, you
       * should simply return from this function -- do not
       * call 'unlock' directly. The 'loop' function will call the
       * 'unlock' function for you. (This will allow the stack to
       * be cleaned up, rather than having a continuously growing
       * function call stack.)
       */
    }

    void unlockFailure() {
      /* You must implement the unlockFailure function
       *
       * This function will flash the "unlocked" LED and make
       * the piezoelectric speaker buzz, as described
       * in the lab documentation. It should do so for
       * approximately 5 seconds, while showing the given
       * message on screen that says a hacker has been
       * detected. After that, we should move back into
       * the "lock" state.
       */
    }
