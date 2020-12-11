+++
title = "Arduino Variables"
description = "Basics of Arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "variables",
    "development",
]
date = "2020-12-08"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Arduino"
+++

# Constants
These are expressions that are predefined in arduino language

* **false** - `false ` is used to define zero.

* **true** -`true` is used to define a non-zero value in programming, mostly 1 but -1 or 200 could also be `true`

* **HIGH** - a pin is said to be High if:
   * a voltage present at the pin is greater than 3.3v (5V boards)
   * a voltage present at the pin is greater than 2.0v (3.3V boards)

* **LOW** -a pin is said to be `low` if:
  * a voltage less than 1.5v  is there in the pin(5v)
  * a voltage less than 1.0v is present at the pin(3.3v)

* **INPUT** -When a pin is set to INPUT, it means that it will permit a relatively small amount of current to pass through it, per unit of the applied voltage at that point.

* **OUTPUT**- When a pin is configured as `OUTPUT` -it means that it would provide a significant amount of current to other circuits

# Conversions

* **(unsigned int)** - modifies a value to `unsigned int` data type.

* **(insigned long)**- modifies a value to `unsigned long` data type.

* **byte()** - modifies a value to a `byte` data type.

* **char()** - modifies a value to a `char` data type.

* **int()** - modifies a value to an `int` data type

* **float()** - modifies a value to an `float` data type

# Data Types

### Array
The array is a list of variables that are accessed by an index number

#### Example 

```
  int myInts[6];
  int myPins[] = {2, 4, 8, 3, 6};
  int mySensVals[6] = {2, 4, -8, 3, 2};
  char message[6] = "hello";

  //accessing an array
  mypins[0] //this is same as 2 in myPins[]  array

  //setting an array

  myInts[0]=1 //same as setting the first value of myInts[] array to be 1

```

### bool

a `bool` holds either of two values, `true` or `false`.

#### Example

```
int LEDpin = 4;     // LED on pin 4
int switchPin = 10; // momentary switch on 10, other side connected to ground

bool running = false;

void setup() {
  pinMode(LEDpin, OUTPUT);
  pinMode(switchPin, INPUT);
  digitalWrite(switchPin, HIGH);  // turn on pullup resistor
}

void loop() {
  if (digitalRead(switchPin) == LOW) {
    // switch is pressed - pullup keeps pin high normally
    delay(100);                     // delay to debounce switch
    running = !running;             // toggle running variable
    digitalWrite(LEDpin, running);  // indicate via LED
  }
}

```

### byte
Byte holds an unsigned 8-bit number, between 0 to 255.

#### Example

```


byte running = 254;

void setup() {

}

void loop() {
}
```
### char
The data-type used to hold a character value. Characters can also be stored as numbers

### Example

```
char myChar = 'A';
char myChar = 65; // both are equivalent

```

### int
The data-type used to store numbers.

#### Example

```
int countUp = 1;            //creates a variable integer called 'countUp'

void setup() {
  Serial.begin(9600);       // use the serial port to print the number
}

void loop() {
  countUp++;                //Adds 1 to the countUp int on every loop
  Serial.println(countUp);  // prints out the current state of countUp
  delay(1000);
}

```

### string

The data-type used to represent text strings

#### Example
{{< highlight Arduino "linenos=table,hl_lines=1-3 1-3, linenostart=1" >}}


char myString[] = "This is the first line"
" this is the second line"
" etcetera";

{{< / highlight >}}

### word

A word can store at least 16 bits of the unsigned numbers (from 0 to 65535) (from 0 to 65535).

#### Example
{{< highlight Arduino "linenos=table,hl_lines=1-2 1-2,linenostart=1" >}}
word w = 10000;

{{< / highlight >}}



