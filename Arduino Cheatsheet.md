# Arduino Cheatsheet

Topics
* [Structure of an Arduino Program](#Structure-of-an-Arduino-Program)
* [Variables](#variables)
* [Functions](#functions)
  * [Built-in](#builtin)
  * [Declaring our own Functions](#declaring-our-own-functions)
  * [Passing Arguments](#passing-arguments)
  * [Returning Values](#returning-values)
* [Loops](#loops)
* [Control Structures](#control-structures)
* [Serial Monitor](#serial-monitor)

---

## Structure of an Arduino Program

```c++
// define your variables here
int ledPin = 13;

void setup() {
    // code called one time
}

void loop() {
    // repeated code
}

// Your defined functions go here
void myFunction() { }
```

## Variables
We can use variables to store values, which makes our code easier to change and easier to read. Variables have a type and that type must be declared.

```c++
int integerVar0 = -10;
int integerVar1 = 7;

float decimalVar = 1.69;

String name = "Jenna";      // make sure to put quotes around Strings

boolean bool0 = true;
boolean bool1 = false;
```

For a concrete example, let's store the pin number for the LED:

```c++
int ledPin = 13;

void setup() {
    pinMode(ledPin, OUTPUT);
}

void loop() {
    digitalWrite(ledPin, HIGH);
}
```


## Functions

### Built-in
* [**setup**()](https://www.arduino.cc/en/Reference/Setup)  
    * code to initialize the Arduino (pinMode() etc.)
* [**loop**()](https://www.arduino.cc/en/Reference/Loop)  
    * code that runs over and over again
* [**pinMode**(pin, OUTPUT)](https://www.arduino.cc/en/Reference/PinMode)  
    * tell the Arduino whether pins are inputs or outputs
* [**delay**(milliseconds)](https://www.arduino.cc/en/Reference/Delay)  

* [**digitalWrite**(pin, HIGH)](https://www.arduino.cc/en/Reference/DigitalWrite)
    * turns pins HIGH or LOW (on/off or 5 volts or 0 volts)
* [**digitalRead**(pin)](https://www.arduino.cc/en/Reference/DigitalRead)  
    * returns whether a pin is HIGH or LOW (on/off, 5 volts or 0 volts)
    * useful for reading buttons
* [**analogWrite**(pin, 255)](https://www.arduino.cc/en/Reference/AnalogWrite)
    * sets a pin to a range of values (0 to 255)
    * useful for fading LEDs
    * only works on pins with "~"
* [**analogRead**(pin)](https://www.arduino.cc/en/Reference/AnalogRead)
    * returns a value between 0 and 1023 (representing 0 volts to 5 volts)
    * only works on the "analog input" pins

### Declaring our own Functions
We can declare our own functions below the loop():

```c++
void setup() {
    // setup code goes here
}

void loop() {
    myFunction();   // call the function you declared below
}

void myFunction() {
    // code goes here
}
```


### Passing Arguments
To pass "arguments to functions" we put them in the paretheses and make sure to declare them in the function definition. For example, to write a function **onOff()** that takes two arguments:

```c++
int ledPin = 13;

void setup() {
    pinMode(ledPin, OUTPUT);
}

void loop() {
    onOff(100, 500);
    onOff(200, 200);
}

void onOff(int delay1, int delay2) {
    digitalWrite(ledPin, HIGH);
    delay(delay1);
    digitalWrite(ledPin, LOW);
    delay(delay2);
}
```

### Returning Values
Sometimes we want to get a value back from a function. In this case, we use the *return* keyword. For example, we can write a function that returns the sum of two arguments:

```c++
int ledPin = 13;

void setup() {
    pinMode(ledPin, OUTOUT);
}

void loop() {
    int sum = add(100, 50);

    digitalWrite(ledPin, HIGH);
    delay(sum);
    digitalWrite(ledPin, LOW);
    delay(sum);
}

void add(int val1, int val2) {
    return val1 + val2;
}
```

**map()**, **analogRead()**, and **digitalRead()** are examples of a built-in functions that returns values, which is why we can set variables equal to these functions:

```c++
int buttonState = digitalRead(buttonPin);
int input = analogRead(lightPin);
int brightness = map(input, 0, 1023, 0, 255);
```

## Loops
[For loops](https://www.arduino.cc/en/Reference/For) allow us to repeat certain code for a specified number of times. Here is the syntax:

![alt text](https://www.arduino.cc/en/uploads/Reference/ForLoopIllustrated.png)

We can use this control structure to make an LED fade in:

```c++
int ledPin = 11;

void setup() {
    pinMode(ledPin, OUTPUT);
}

void loop() {
    fadeIn();
}

void fadeIn() {
    for (int i = 0; i < 255; i++) {
        analogWrite(ledPin, i);
    }
}
```

## Control Structures
We can use conditional logic to add complexity to our sketches.
* [if / else if / else](https://www.arduino.cc/en/Reference/Else)
* Make sure to use "==" to test for equality

```c++

int inputPin = A0;

void setup() {
    pinMode(inputPind, INPUT);
}

void loop() {
    checkSign();
}

void checkSign() {
    int x = analogRead(inputPin);
    if (x > 0) {
        Serial.println("Positive!");
    }
    else if (x == 0) {
        Serial.println("Zero!");
    }
    else {
        Serial.println("Negative!");
    }
}
```

## Serial Monitor
Sometimes we want to print values that the Arduino is reading to our computer screen. For example, we might want to know what kind of reading our light sensor is getting. The following functions will print values to the screen:

```c++
void setup() {
    Serial.begin(9600);
}

void loop() {
    Serial.print("Input is: ");
    Serial.println(analogRead(A0));
}
```

* Serial.begin() tells the computer to communicate with the Arduino
* Serial.print() will print something on the same line
* Serial.println() prints and creates a new line

## Common Circuits

### LED Fade

![alt text] (Notes/images/ledfade.png)


### Light Sensor Circuit

![alt text](https://cdn-learn.adafruit.com/assets/assets/000/000/459/original/light_cdspulldowndiag.gif?1447975687)

### Pushbutton

![alt text] (https://lh3.googleusercontent.com/NAipfzKrTgsqNRtxh68_uI8Fmvb6d_lvNedSJgoV3NUvbC4apZFt9vZCSGRvd4jPPFXAbxOcpVkDlIHcsDG_RcOb3if-SsisEsqAiGIvsZc7MDn1pA4IIJK8UbgAWbhF0iPdb7vc)
