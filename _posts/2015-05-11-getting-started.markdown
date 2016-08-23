---
layout: post
title:  "Getting started with Arduino!"
date:   2015-05-11 12:37:30
categories: others
---

To get started with Apollo, you need to download and install the Arduino IDE.

Debian / Ubuntu Linux:

1. Open a terminal and type `sudo apt-get install arduino`
  1. The version contained in the repos is likely *heavily* outdated, but it installs all needed dependencies.
2. Next, [download][ArduinoIDE] the Linux version appropriate to your CPU architecture.
3. Use `tar -xvf arduino-*-linux*.tar.xz` or some other method to extract it in a convenient location.
4. Using a terminal, `cd` into the arduino directory, and run `./arduino` to start the IDE.

Mac OS X:

1. [Download it from here][ArduinoIDE]
2. Move the Arduino.app that is extracted from the zip into the Applications folder
3. There is no step three.

Windows:

1. [Download it from here][ArduinoIDE]
2. Install it like any other program.
3. You will probably need to follow [these instructions][Instructions] to install additional drivers.
  1. [This page][ScreenshotTutorial] is slightly outdated, but could be helpful.

Now that the Arduino IDE is installed, it is time to make sure everything is working.

1. Open the IDE
2. Go to File -> Examples -> 01.Basics -> Blink
3. Go to Tools -> Serial Port and then click on the Arduino
3. Click the button in the toolbar that looks like an arrow facing to the right.

If your Arduino IDE is configured correctly and your Apollo is plugged in, you should have an LED blinking on it now.

Now lets test out the display, copy and past the folowing code into the Arduino ide.

```
#include <LiquidCrystalShift.h>   //This line of code creates a global instance of the LCD module
LiquidCrystalShift lcd(7, 8, A3); //The next thing that needs to be done is to place "lcd.begin(16, 2)"
                                  //in your setup function, as shown below
void setup() {
    lcd.begin(16, 2); //This line sets up the display
}

//Inside your loop function, or anywhere else, you can display
//text and values on the screen by using print statements
void loop() { 
    lcd.setCursor(0, 0); //resets the cursor to the top left of the screen 
    lcd.print("Hello World!"); //prints the word "Apollo!" to the screen
}
```

If you run the code now, you should see Hello, World on the display!


[ArduinoIDE]:         http://www.arduino.cc/en/Main/Software
[Instructions]:       http://www.arduino.cc/en/Guide/Windows#toc4

