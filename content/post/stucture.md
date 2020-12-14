+++
title = "Structure of Arduino"
description = "Basics of Arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "electronics",
    "structure",
]
date = "2020-12-14"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Arduino structure"
+++

# Structure of Arduino

## THE SKETCH(arduino program)

An arduino program frequently known  as SKETCH is composed of two functions
  * loop()
  * setup()

### setup()
The setup() function is normally called when the sketch begins.
It usually used to initialize pin modes and variables

#### Example

{{< highlight Arduino "linenos=table,hl_lines=1-10 1-10, linenostart=1" >}}
int buttonPin = 3;

void setup() {
  Serial.begin(9600);
  pinMode(buttonPin, INPUT);
}

void loop() {
  // ...
}


{{< / highlight >}}

### loop()
The loop function loops through the code consectutively allowing the program to adapt and change

{{< highlight Arduino "linenos=table,hl_lines=1-24 1-24, linenostart=1" >}}
int buttonPin = 3;

// setup initializes serial and the button pin
void setup() {
  Serial.begin(9600);
  pinMode(buttonPin, INPUT);
}

// loop checks the button pin each time,
// and will send serial if it is pressed
void loop() {
  if (digitalRead(buttonPin) == HIGH) {
    Serial.write('H');
  }
  else {
    Serial.write('L');
  }

  delay(1000);
}
{{< / highlight >}}