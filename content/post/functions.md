+++
title = "Arduino Functions"
description = "Basics of Arduino"
author="Denis Kiprono"
tags = [
    "arduino",
    "basics",
    "electronics",
    "development",
]
date = "2020-12-09"
categories = [
    "Arduino",
    "Electronics",
]
menu = "Arduino"
+++

# Digital IO

**digitalRead()-** it reads a value from an specific pin as either HIGH OR LOW

### Example code

```

void setup() {

  pinMode(7, INPUT);    // sets the digital pin 7 as input
}

void loop() {
  val = digitalRead(7);   // read the input pin

}


```

**digitalWrite() -** -It writes `HIGH` OR `LOW` value to a digital pin


### Example

```
void setup() {
  pinMode(12, OUTPUT);    // sets the digital pin 12 as output
}

void loop() {
  digitalWrite(12, HIGH); // sets the digital pin 12 on
  delay(1000);            // waits for a second
  digitalWrite(12, LOW);  // sets the digital pin 12 off
  delay(1000);            // waits for a second
}


```

**pinMode() -** -it sets specified pin to behave as input or output


### Example

```
void setup() {
  pinMode(5, OUTPUT);    // sets the digital pin 5 as output
}

void loop() {
//add your code here
}



```

# Analog I/O

**analogRead() -** Reads a value from a specific analog pin.

### Example
```
int analogPin = A3; // potentiometer wiper (middle terminal) connected to analog pin 3
                    // outside leads to ground and +5V
int val = 0;  // variable to store the value read

void setup() {

}

void loop() {
  val = analogRead(analogPin);  // read the input pin
  
}

```

**analogWrite() -** -it is used to write a value into a specified pin. It is normally used to control motor speeds or brightness of a led

### Example
```
int ledPin = 9;      // LED connected to digital pin 9
int analogPin = 3;   // potentiometer connected to analog pin 3
int val = 0;         // variable to store the read value

void setup() {
  pinMode(ledPin, OUTPUT);  // sets the pin as output
}

void loop() {
  val = analogRead(analogPin);  // read the input pin
  analogWrite(ledPin, val / 4); // analogRead values go from 0 to 1023, analogWrite values from 0 to 255
}


```

# Advanced I/O Functions

**pulseIn() -**- Reads a pulse (either HIGH or LOW) on a pin. For example, if value is HIGH, pulseIn() waits for the pin to go from LOW to HIGH, starts timing, then waits for the pin to go LOW and stops timing. In otherwords, it records the duration it takes to move form HIGH to LOW.

### Example

```
int pin = 7;
unsigned long duration;

void setup() {
  Serial.begin(9600);
  pinMode(pin, INPUT); //sets pin 7 as input
}

void loop() {
  duration = pulseIn(pin, HIGH);
  Serial.println(duration);
}

``` 

# Time Functions

**Delay  -** Pauses the program for specified amount of time (in milliseconds) .

### Example

```
int ledPin = 12;              // LED connected to digital pin 12

void setup() {
  pinMode(ledPin, OUTPUT);    // sets the digital pin as output
}

void loop() {
  digitalWrite(ledPin, HIGH); // sets the LED on

  delay(1000);                // waits for a second

  digitalWrite(ledPin, LOW);  // sets the LED off

  delay(1000);                // waits for a second
}

```

**delayMicroseconds() -** pauses a program for specified duration in Microseconds

### Example

```
int outPin = 4;               // digital pin 4

void setup() {
  pinMode(outPin, OUTPUT);    // sets the digital pin as output
}

void loop() {
  digitalWrite(outPin, HIGH); // sets the pin on

  delayMicroseconds(50);      // pauses for 50 microseconds

  digitalWrite(outPin, LOW);  // sets the pin off

  delayMicroseconds(50);      // pauses for 50 microseconds
}


```

**micros() -** - it returns duration in microseconds since the Arduino board began executing the current program.

```

unsigned long time;

void setup() {
  Serial.begin(9600);
}

void loop() {
  Serial.print("Time: ");

  time = micros();

  Serial.println(time); //prints time since program started

  delay(1000);          // wait a second so as not to send massive amounts of data
}

```

**millis() -** -Returns the duration in milliseconds since arduino started running the current program.


# Serial Functions
**Serial.begin() -** - Sets the data rate in bits per second (baud) for serial data transmission (communicating with Serial Monitor)

### Example
```
void setup() {
    Serial.begin(9600); // opens serial port, sets data rate to 9600 bps
}

void loop() {}

```


**Serial.end() -** - it Disables serial communication.

### Example
```
void setup() {
    Serial.end(); // closes serial port, sets data rate to 9600 bps
}

void loop() {}

```

**Serial.print() -** -writes data to the serial port in human-readable form(text).

### Example
```
void setup() {
    Serial.begin(9600); // closes serial port, sets data rate to 9600 bps
}

void loop() {
	
	Serial.print("Hallo world");
}

```

**Serial.read() -**-it reads incoming serial data.

### Example
```
void setup() {
    Serial.begin(9600); // closes serial port, sets data rate to 9600 bps
}

void loop() {
	int data= Serial.read();
	Serial.print(data);
}

```