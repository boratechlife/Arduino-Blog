+++
title = "Control Structures in Arduino"
description = "Basics of Arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "electronics",
    "control structure",
]
date = "2020-12-14"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Arduino structure"
+++

# Control Structure

## `break`
it is used to exit from loop conditions or switch statement.

### Example
{{< highlight Arduino "linenos=table,hl_lines=1-10 1-10, linenostart=1" >}}
int threshold = 40;
for (int x = 0; x < 255; x++) {
  analogWrite(PWMpin, x);
  sens = analogRead(sensorPin);
  if (sens > threshold) {     // bail out on sensor detect
    x = 0;
    break;
  }
  delay(50);
}
{{< / highlight >}}

##  continue
It is simply used to skip an iteration based on certain condition. Skipping to next iteration

{{< highlight Arduino "linenos=table,hl_lines=1-10 1-10, linenostart=1" >}}
for (int x = 0; x <= 255; x ++) {
  if (x > 40 && x < 120) {  // create jump in values
    continue;
  }

  analogWrite(PWMpin, x);
  delay(50);
}
{{< / highlight >}}

## while loop
it is a type of loop that will continuously execute until the condition inside the paranthesis is `false`.

### Example
{{< highlight Arduino "linenos=table,hl_lines=1-10 1-10, linenostart=1" >}}
var = 0;
while (var < 200) {
  // do something repetitive 200 times
  var++;
}

{{< / highlight >}}

## do...while loop
It is equivalent to while the loop except that the condition is executed at the end of the loop. This means that the loop will be executed at least once.

### Example

{{< highlight Arduino "linenos=table,hl_lines=1-5 1-5, linenostart=1" >}}
int x = 1;
do {
  delay(50);          // wait for sensors to stabilize
  x = readSensors();  // check the sensors
} while (x < 10);
{{< / highlight >}}

## `if`
`If` the statement checks the condition and executes the code inside curly braces, if the condition is `true`.

## 'else'

`else ` statement is executed whenever an if condition is false. It can be chained to form a bunch of `if..else` statements when there many conditions involved.


## Example
{{< highlight Arduino "linenos=table,hl_lines=1-10 1-10, linenostart=1" >}}

if (temperature >= 70) {
  // Danger! Shut down the system.
}
else if (temperature >= 60) { // 60 <= temperature < 70
  // Warning! User attention required.
}
else { // temperature < 60
  // Safe! Continue usual tasks.
}

{{< / highlight >}}


## for loop
The for statement is used to loop a sequence of code wrapped within curly braces.

### Example

{{< highlight Arduino "linenos=table,hl_lines=1-15 1-15, linenostart=1" >}}

// Dim an LED using a PWM pin
int PWMpin = 10;  // LED in series with 470 ohm resistor on pin 10

void setup() {
  // no setup needed
}

void loop() {
  for (int i = 0; i <= 255; i++) {
    analogWrite(PWMpin, i);
    delay(10);
  }
}

{{< / highlight >}}

## `goto`
Transfers a program flow to a defined point of the program.

### Example
{{< highlight Arduino "linenos=table,hl_lines=1-15 1-15, linenostart=1" >}}

for (byte r = 0; r < 255; r++) {
  for (byte g = 255; g > 0; g--) {
    for (byte b = 0; b < 255; b++) {
      if (analogRead(0) > 250) {
        goto bailout;
      }
      // more statements ...
    }
  }
}

bailout:
// more statements ...

{{< / highlight >}}

## return
End a function and if desired, return the value from the function

### Example
{{< highlight Arduino "linenos=table,hl_lines=1-15 1-15, linenostart=1" >}}

int checkSensor() {
  if (analogRead(0) > 400) {
    return 1;
  }
  else {
    return 0;
  }
}
{{< / highlight >}}

## `switch case`
Switch case controls the flow of programs by allowing programmers to define a particular code that must be executed in various conditions.

### Example
{{< highlight Arduino "linenos=table,hl_lines=1-15 1-15, linenostart=1" >}}
switch (var) {
  case 1:
    //do something when var equals 1
    break;
  case 2:
    //do something when var equals 2
    break;
  default:
    // if nothing else matches, do the default
    // default is optional
    break;
}
{{< / highlight >}}