# 6. digitalRead()

Topics
* [I. Serial Monitor](#i-serial-monitor)
* [II. Analog Input Pins](#ii-analog-input-pins)
* [III. Light Sensor](#iii-light-sensor)

Exercises
* [Exercise 0](#ex0)
* [Exercise 1](#ex1)
* [Exercise 2](#ex2)

---

## I. Pushbutton
In this example, we're going to use [**digitalRead()**](https://www.arduino.cc/en/Reference/DigitalRead) to check whether a button is HIGH or LOW (i.e. on or off, 5 volts or 0 volts, true or false). Unlike analogRead(), digitalRead() doesn't return a range of values- it simply *returns* whether the pin is on or off.

Begin by setting up the circuit:

![alt text](images/pushb.png)


```c++
int ledPin = 13;
int buttonPin = 2;

void setup() {
    pinMode(ledPin, OUTPUT);
    pinMode(buttonPin, INPUT);    // NOTE THE BUTTON IS INPUT
}

void loop() {
    boolean state = digitalRead(buttonPin);
    if ( state == HIGH ) {
        digitalWrite(ledPin, HIGH);
    }
    else {
        digitalWrite(ledPin, LOW);
    }
}
```

---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
Write a function <b>timer()</b> that takes an argument and keeps an LED
on for the amount of time passed to the function. Call this function
when a button is pressed.
</pre>

```c++
int ledPin = 13;
int buttonPin = 2;

void setup() {
    pinMode(ledPin, OUTPUT);
    pinMode(buttonPin, INPUT);    // note the button is INPUT
}

void loop() {
    boolean state = digitalRead(buttonPin);

    // if / else statement here
}

// define timer() here
```

---

## II. Latching Button

Now the objective is to make a button that stays on when we first click it, and turns off when we click it again. We can use boolean variables 
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
