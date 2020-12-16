+++
title = "Further Syntax "
description = "Basics of Arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "syntax",
    "electronics",
    "control structure",
]
date = "2020-12-13"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Arduino Further Syntax"
+++

# Further Syntax

## `#define`
Allows the programmer to assign a name to a constant value.

### Example



``` arduino {linenos=table,hl_lines=[2,"1-17"],linenostart=1}
#define ledPin 3
// The compiler will replace any mention of ledPin with the value 3 at compile time.

```

## `#include`
it is used to include external libraries into arduino program

### Example

``` ino {linenos=table,hl_lines=[2,"1-30"],linenostart=1}
#include <Servo.h>

Servo myservo;  // create servo object to control a servo

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
}

void loop() {
  for (int pos = 0; pos <= 180; pos += 1) { // goes from 0 degrees to 180 degrees
    // in steps of 1 degree
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15ms for the servo to reach the position
  }
  for (int pos = 180; pos >= 0; pos -= 1) { // goes from 180 degrees to 0 degrees
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15ms for the servo to reach the position
  }
}


```

## Comments

 Block comments are written inside these symbols: /* */

 ### Example
 /* This is a valid comment */

``` arduino {linenos=table,hl_lines=[10,"1-30"],linenostart=1}
/*
  Blink
  Turns on an LED on for one second, then off for one second, repeatedly.

  This example code is in the public domain.
  (Another valid comment)
*/

/*
  if (gwb == 0) { // single line comment is OK inside a multi-line comment
    x = 3;          /* but not another multi-line comment - this is invalid */
  }
// don't forget the "closing" comment - they have to be balanced!
*/
```