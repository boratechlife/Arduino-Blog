+++
title = "Ky-037 sound sensor with Arduino"
description = "Interfacing KY-037 Sound sensor with arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "ky-037 sound sensor"
]
date = "2020-12-21"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Connecting KY-037 Sound sensor with Arduino"
+++
It consist of a capacitive microphone and an amplifier.The output of this module is both analog and digital.

## Pins
This module contains 4 pins, 2 of the are used to supply power.
pin 1: anaog ouput and pin 4: digital output-activates when sound reaches certain threshold.


## Components Required
- Arduino uno
- KY-037 Sound sensor
- 4 jumper wires


## Procedure

1. Set up your connection as shown in the followinf image.

![joy stick connecting image](/sound-sensor-image.jpg)

2. Connect ground pin to ground

3. Connect positive pin to arduino 5v
4. Connect A0 to 'A0' in the arduino board


5. In the `setup()`
``` ino {linenos=table,hl_lines=[4,"1-30"],linenostart=1}
void setup() {
  // initialize serial communication at 9600 bits per second:
  Serial.begin(9600);
}
```

6. In the `loop()` function write:
``` ino {linenos=table,hl_lines=[10,"1-30"],linenostart=1}

// the loop routine runs over and over again forever:
void loop() {
  // read the input on analog pin 0:
  int sensorValue = analogRead(A0);
  // print out the value you read:
  Serial.println(sensorValue);
} 
```


### Full source Code
``` ino {linenos=table,hl_lines=[2,"1-36"],linenostart=1}
void setup() {
  // initialize serial communication at 9600 bits per second:
  Serial.begin(9600);
}

// the loop routine runs over and over again forever:
void loop() {
  // read the input on analog pin 0:
  int sensorValue = analogRead(A0);
  // print out the value you read:
  Serial.println(sensorValue);
} 
```