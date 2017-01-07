# 2. analogWrite()

## 0. Overview

|  | Topics | Exercises | Circuit |
| --- | --- | --- | --- |
| I | [Defining Functions](#i-builtin-functions) | [Exercise 0](#ex0) <br/> [Exercise 1](#ex1) | LED resistor |
| II | [RGB LEDs](#ii-rgb-leds)| [Exercise 2](#ex2) | RGB LED |


## I. Built-in Functions

So far we've looked at the following built-in functions (we'll define functions in the next chapter):

* [setup()](https://www.arduino.cc/en/Reference/Setup)
  Every Arduino sketch must have a setup()- called one time at the beginning.
* [loop()](https://www.arduino.cc/en/Reference/Loop)
  Every Arduino sketch must have a loop()- called over and over as long as the Arduino is plugged in.
* [digitalWrite(pin, HIGH/LOW)](https://www.arduino.cc/en/Reference/DigitalWrite)
  Turns LEDs ON/OFF
* [delay()](https://www.arduino.cc/en/Reference/Delay)
  Delays for a number of milliseconds (1000 milliseconds/second)

We're going to look at another built-in function: **analogWrite()**. Like digitalWrite(), analogWrite() can be used to power LEDs, but in this case, analogWrite() can *set a range of values between 0-255, not just ON/OFF,* making it possible to fade LEDs.

```c++
// takes a pin number and a value between 0-255
analogWrite(pin, value);
```

---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
Only ~ pins (pulse width modulation pins) can use the function analogWrite().
Which pins can do analog writes?
</pre>

---

Let's use analogWrite() in an example to turn an LED to half brightness. Setup the following circuit:

| Circuit | Materials | Diagram |
| --- | --- | --- |
| LED resistor | <ul><li>2 jumpers</li><li>220Ω resistor</li><li>LED</li><li>breadboard</li></ul> | ![alt text](../images/arduinores.jpg) |

Here's the code:

```c++
int ledPin = 9; // 9 is a pin with a ~

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  analogWrite(ledPin, 255/2);         
}
```

---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
1. Use the circuit in the previous example.

2. Make the LED:
    1) start off
    2) 1/3 max brightness
    3) 2/3 max brightness
    4) full brightness
    5) repeat!
</pre>

```c++
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // off
  // 1/3 max brightness
  // 2/3 max brightness
  // max brightness
}
```

## II. RGB LEDs
RGB LEDs are LEDs with a red, green, and blue diode. Together, these diodes can produce any color of the rainbow! We treat RGB LEDs as if they were three separate LEDs and we program them individually.

Begin by setting up the following circuit:

| Circuit | Materials | Diagram |
| --- | --- | --- |
| RGB LED | <ul><li>4 jumpers</li><li>3, 220Ω resistors</li><li>RGB LED</li><li>breadboard</li></ul> | ![alt text](../images/rgb.jpg) |

```c++
int redPin = 11;
int greenPin = 10;
int bluePin = 9;

void setup() {
  // pinMode for each LED
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);  
}

void loop() {
  // makes the color green
  analogWrite(redPin, 0);
  analogWrite(greenPin, 255);
  analogWrite(bluePin, 0);  
}
```

---

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
Use a <a href="http://www.w3schools.com/colors/colors_picker.asp">online color picker</a> to find the R, G, & B values of
your favorite color and set the RGB LED to that color.
</pre>
