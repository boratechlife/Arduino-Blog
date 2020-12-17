+++
title = "Fading A Led"
description = "Basics of Arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "Led",
    "analogWrite",
]
date = "2020-12-17"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Fading A Led"
+++
 This tutorial intends to demonstrate how to fade light on and off with arduino.
 To accomplish this, we shall use `analogWrite` function which uses pulse Width Modulation(PWM) to vary the light state.

 ## Components Required

 -  Arduino Board
 - LED
 - 220 ohm Resistor
 - Wires
 -  Breadboard


## Connection Preview
![Simple Fade](/simplefade.png)

 ## Procedure

 - Connect the anode (the longer, positive leg) of your LED to digital output pin 9 on your board through a 220 ohm resistor
 - Connect the cathode (the shorter, negative leg) directly to ground.
 - Open the Editor(if you haven't)
 - Before Setup function declare the following variables
 ```
int led = 9;           // the PWM pin the LED is attached to
int brightness = 0;    // how bright the LED is
int fadeAmount = 5;    // how many points to fade the LED by

 ```
 - In the setup function declare pin 9 to be an output
 ```
  pinMode(led, OUTPUT);

 ```
-  in the loop function, set the brightness of pin 9
```
 analogWrite(led, brightness);
```
-  Then change the brightness, using fadeAmount
```
  brightness = brightness + fadeAmount;
```

- Reverse the direction of the fading at the *ends* of the fade
```
  if (brightness <= 0 || brightness >= 255) {
    fadeAmount = -fadeAmount;
  }
```
- wait for 30 milliseconds to see the dimming effect
```
delay(30);
```

## Full Source Code
``` ino {linenos=table,hl_lines=[30,"1-30"], linestart=1}
int led = 9;           // the PWM pin the LED is attached to
int brightness = 0;    // how bright the LED is
int fadeAmount = 5;    // how many points to fade the LED by

// the setup routine runs once when you press reset:
void setup() {
  // declare pin 9 to be an output:
  pinMode(led, OUTPUT);
}

// the loop routine runs over and over again forever:
void loop() {
  // set the brightness of pin 9:
  analogWrite(led, brightness);

  // change the brightness for next time through the loop:
  brightness = brightness + fadeAmount;

  // reverse the direction of the fading at the ends of the fade:
  if (brightness <= 0 || brightness >= 255) {
    fadeAmount = -fadeAmount;
  }
  // wait for 30 milliseconds to see the dimming effect
  delay(30);
}


```