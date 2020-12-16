+++
title = "Arduino Blinking Led"
description = "Basics of Arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "operators",
    "blinking led",
]
date = "2020-12-15"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Arduino Blinking Led"
+++

Leds are tiny powerful lights that are used in various applications. In these tutorial we shall discuss how to light a blinking led - a hello world program of arduino.

## Components Required
- Breadboard
- Arduino Mega 2560(any board you have can work. This tutorial will used Arduino Mega 2560)
- Led
- 330 ohm Resistor
- 2 jumper wired

## Procedure

1. Set up your connection as shown in the followinf image.

![blinking led](/blinking_led.png)

2. Connect your Arduino Board to your Computer

3. Start Arduino IDE

4. Once the Editor is open, Begin by writing the following code in the setup function:
``` ino {linenos=table,hl_lines=[2,"1-30"],linenostart=1}
pinMode(LED_BUILTIN, OUTPUT);

```

5. In the `loop()` function write:
``` ino {linenos=table,hl_lines=[2,"1-30"],linenostart=1}
digitalWrite(LED_BUILTIN, HIGH);

delay(1000)//delay for 1 second

  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW

  delay(1000);                       // wait for a second

```


### Full source Code
``` ino {linenos=table,hl_lines=[2,"1-30"],linenostart=1}

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}


```