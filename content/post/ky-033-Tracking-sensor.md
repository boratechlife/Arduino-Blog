+++
title = "Ky-033 Tracking with Arduino"
description = "Interfacing KY-033 Tracking with arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "KY-033 Tracking"
]
date = "2020-12-22"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Connecting KY-033 Tracking with Arduino"
+++
We are going to detect white line using a KY-033 Sensor.

## Pins
This module has 3 pins.GRD, OUT, VCC.


## Components Required
- Arduino uno
- KY-033 Tracking Sensor
- 3 jumper wires


## Procedure

1. Set up your connection as shown in the followinf image.

![joy stick connecting image](/tracking_sensor.avif)

2. Connect ground pin to ground

3. Connect positive pin to arduino 5v
4. Connect output to 'A5' in the arduino board


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
  // read the input on analog pin 5
  int sensorValue = analogRead(A5);
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
  // read the input on analog pin 5:
  int sensorValue = analogRead(A5);
  // print out the value you read:
  Serial.println(sensorValue);
} 
```