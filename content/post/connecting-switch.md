+++
title = "Reading From Switch"
description = "Basics of Arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "switch",
    "Digital signal",
]
date = "2020-12-17"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Reading From Switch"
+++
This tutorial will explain how to connect a switch to arduino board and read its state.

### Components Required
- Arduino Board
- Switch
- Wires
- BreadBoard
- 10 ohm Resistor

### Connection Preview
![Button](/button.png)

PROCEDURE
- Connect a ground of an arduino to negative part rail of the breadboard.
- Connect 5v pin to the positive part rail of the breadboard.
- Connect Digital pin 2 to one of the legs of the switch.
- On the same leg, connect 10 ohm resistor to ground.
- Connect the other leg of the switch to 5v(positive part of breadboard).
- Open Arduino Editor(If you have not done it).
- On the setup function type:
```
Serial.begin(9600)
```

- On the same function initialize digital pin 2, the pin that will read the output from your button, as an input:

```
pinMode(2,INPUT);
```
-  Initialize the variable to Read the value.
```
int sensorValue = digitalRead(2);
```
- Print the value to the Serial

```
Serial.println(sensorValue);
```
## Full Source Code

```ino {linenos=table,hl_lines=[8,"1-21"],linestart=1}

int pushButton = 2;

// the setup routine runs once when you press reset:
void setup() {
  // initialize serial communication at 9600 bits per second:
  Serial.begin(9600);
  // make the pushbutton's pin an input:
  pinMode(pushButton, INPUT);
}

// the loop routine runs over and over again forever:
void loop() {
  // read the input pin:
  int buttonState = digitalRead(pushButton);
  // print out the state of the button:
  Serial.println(buttonState);
  delay(1); // delay in between reads for stability
}


```