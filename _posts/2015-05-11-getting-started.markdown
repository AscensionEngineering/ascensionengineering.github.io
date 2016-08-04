---
layout: post
title:  "Getting started with Arduino!"
date:   2015-05-11 12:37:30
categories: docs
---

To get started with Arduino, you need to download and install the Arduino IDE.

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

If your Arduino IDE is configured correctly and your Arduino is plugged in, you should have an LED blinking on it now.

We want to check the LCD Shield, so plug it into the Arduino now, and we'll create a short little program to use it. When you connect the LCD Shield, it should fit down all the way onto the Arduino, with little or no copper from the pins showing after being pushed into the socket. This may take some force, just be careful not to break anything.

Create a new sketch by clicking on File -> New. Before the first line, which says `void setup() {`, we want to put these lines:

    #include <LiquidCrystal.h>
    LiquidCrystal lcd(8, 9, 4, 5, 6, 7);           // select the pins used on the LCD panel

That last line of code will make a new variable called `lcd` that will handle all of the talking with our LCD shield. Now, after the line that says `void setup() {`, let's put the following code:

    lcd.begin(16, 2); //it is a 16 x 2 character display
    lcd.print("Hello, World!");

If you run the code now, you should see Hello, World on your shield! If not, we need to figure out why.

Submit your code to Dropbox.

[ArduinoIDE]:         http://www.arduino.cc/en/Main/Software
[Instructions]:       http://www.arduino.cc/en/Guide/Windows#toc4
[ScreenshotTutorial]: http://www.arduino.cc/en/Guide/UnoDriversWindowsXP
