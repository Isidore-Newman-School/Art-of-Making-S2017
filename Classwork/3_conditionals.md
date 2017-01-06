# 2. Night Light

We've used the following built-in functions to turn LEDs on/off:
* digitalWrite()
* analogWrite()

Now it's time to learn about reading sensors.

## Circuit
Begin by setting up the following circuit:

![alt text](http://s4a.cat/examples/photoresistor_led.png)

## analogRead()
We're going to use a new function, [analogRead()](https://www.arduino.cc/en/Reference/AnalogRead), to get a value from the light sensor. analogRead() takes a pin number as an argument and returns a number between 0 and 1023- 0 represents 0 volts and 1023 represents 5 volts.

We're going to set the variable "input" equal to the light reading. Eventually, we'll use this value to determine whether or not to turn on the night light (LED).

```c++

int ledPin = 13;
int lightPin = A0;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(lightPin, INPUT);
}

void loop() {
  int input = analogRead(lightPin);
}
```

## Serial.println()
Cool! We're reading the value of the light sensor, but unless we print it to the screen, we have no idea if it's working. Time to use the Serial Monitor! Add the following line to your setup():

```c++
void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(lightPin, INPUT);

  // tell the Arduino at what speed to communicate with computer
  Serial.begin(9600);
}
```

Now we can print the value to the screen with **Serial.println()**:
```c++
void loop() {
  int input = analogRead(lightPin);
  Serial.println(input);
}
```

When you open your Serial Monitor, you should see the values printed ot the screen.

![alt text](https://camo.githubusercontent.com/e926b7f0e8f6b818436d0d8bf6f93057f33f4ab6/687474703a2f2f617263626f746963732e636f6d2f686f7374696e672f6c742f696d616765732f5475746f7269616c732f53657269616c5f4d6f6e69746f72312e706e67)

## if / else
Now it's time to create the nightlight. We want the LED to come on when the light in the room goes dim. We will use a very useful structure in computer science: if / else statment.

```c++

int ledPin = 13;
int lightPin = A0;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(lightPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  int input = analogRead(lightPin);
  Serial.println(input);

  // if the light sensor reading is low, turn on LED
  if (input < 400) {
    digitalWrite(ledPin, HIGH);
  }
  // otherwise ...
  else {
    digitalWrite(ledPin, LOW);
  }
}
```

# 3. Pushbutton

We've looked at the following functions:

* digitalWrite()
* analogWrite()
* analogRead()

In this example, we're going to use [**digitalRead()**](https://www.arduino.cc/en/Reference/DigitalRead) to check whether a button is HIGH or LOW (i.e. on or off, 5 volts or 0 volts). Unlike analogRead(), digitalRead() doesn't return a range of values- it returns whether the pin is on or off.

## The Circuit

![alt text](images/pushb.png)

## Code
```c++
int ledPin = 13;
int buttonPin = 2;

void setup() {
    pinMode(ledPin, OUTPUT);
    pinMode(buttonPin, INPUT);
}

void loop() {
    if (digitalRead(buttonPin) == HIGH) {
        // if the button is HIGH/ on, turn the LED on
        digitalWrite(ledPin, HIGH);
    }
    else {
        digitalWrite(ledPin, LOW);
    }
}
```


**(4)** Use an [if / else if/ else](https://www.arduino.cc/en/Reference/Else) structure to Serial.println() "Positive!" if x is positive, "Zero!" if x is zero, and "Negative!" if x is negative. Check the result in the Serial Monitor.

**(1)** In computer science the "%" (a.k.a. the modulo operator) is surprisingly useful. It is used to calculate the remainder after dividing two numbers. E.g.:

    5%2 = 1;
    4%2 = 0;
    3%2 = 1;
    2%2 = 0;
    1%2 = 1;
    0%2 = 0;

Use the modulo operator to write a function **fizzBuzz()** that uses Serial.print() to print the numbers from 1 to 100, with two exceptions:

1. For numbers divisible by 3, print "Fizz" instead of the number
2. For numbers divisible by 5 (and not 3), print "Buzz" instead.

```c++
void setup() {
    pinMode(ledPin, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    fizzBuzz();
}

void fizzBuzz() {

}
```



2) Fill out the following function, **checkPiezoHit()** so that if:
* hit is less than 100, turn LED off.
* hit is less than 200, turn LED 10% on.
* hit is less than 500, turn LED 50% on.
* hit is over 500, turn LED 100% on.

```c++
int ledPin = 11;
int piezoPin = A0;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(piezoPin, INPUT);
}

void draw() {
  checkPiezoHit();
}

void checkPiezoHit() {
  int hit = analogRead(piezoPin);

  if (            ) {

    analogWrite(ledPin, 0);
  }
  else if (            ) {



  }
  else if (            ) {



  }
  else {



  }
}
```

3) Check a light sensor. If its value is less than 400, blink an LED. Otherwise, turn it off.

```c++
int ledPin = 13;
int lightPin = A0;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void draw() {
  checkLight();
}

void checkLight() {
  int lightLevel = analogRead(lightPin);


















}
```

Write a function **timer()** that takes an argument and keeps an LED on for the amount of time passed to the function. Call this function when a button is pressed.
