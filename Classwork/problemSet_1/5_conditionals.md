# 5. Conditionals

## 0. Overview

|  | Topics | Exercises | Circuit |
| --- | --- | --- | --- |
| I | [if / else](#i-if--else) | [Exercise 0](#ex0) | light sensor |
| II | [if / else if / else](#ii-if--else-if--else) | [Exercise 1](#ex1) | light sensor |
| III | [Booleans](#iii-booleans) | [Exercise 2](#ex2) | light sensor |

## I. if / else
Conditional statements are used across all programming languages to add logic to code. In the example below, we will check if x is greater than 10:

```c++
void setup() {
  Serial.begin(9600);
}

void loop() {
  greaterThan10(-4);
  greaterThan10(5);
}

void greaterThan10(int x) {
  if (x > 10) {
    Serial.println("x is greater than 10!");
  }
  else {
    Serial.println("x is less than or equal to 10!");
  }
}
```

---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
We're going to create a night light. Begin by setting up the circuit below.

To create a night light, the LED must come on when the light in the room goes dim. Fill out the missing
code in the code block below in order to create the night light:
</pre>

| Circuit | Materials | Diagram |
| --- | --- | --- |
| light sensor | <ul><li>photoresistor (light sensor)</li><li>3 jumpers wires</li><li>10KΩ resistor</li><li>LED</li><li>breadboard</li></ul> | ![alt text](http://s4a.cat/examples/photoresistor_led.png) |


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


  if ( ) {
    // if the light sensor reading is low, turn on LED
  }

  else {
    // otherwise, turn off the LED
  }
}
```

---

## II. if / else if / else
Sometimes you want to test more than just 2 conditions. In these cases, you can use an arbitrary number of "else if" statements. Let's say we want to check if x is positive, negative, or zero.

**NOTE** The "==" operator, not "=", is used for testing equality.

```c++
void setup() {
  Serial.begin(9600);
}

void loop() {
  checkIfPositive(-4);
  checkIfPositive(0);
  checkIfPositive(5);
}

void checkIfPositive(int x) {
  if (x > 0) {
    Serial.println("positive!");
  }
  else if (x == 0) {
    Serial.println("zero!");
  }
  else {
    Serial.println("negative!");
  }
}
```

---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
Using the night light circuit from the previous exercise, use an if / else if / else statement to create
three separate cases:

1. if the light is really dim (e.g. hand covering sensor), turn the LED on and print, "sleepy time".
2. if the light is dim, turn the LED on and print "sunset or sunrise" to the Serial Monitor
3. if the light in the room is on, turn the LED off and print, "awake!".
</pre>

---

## III. Boolean Operators
We can use [boolean operators](https://www.arduino.cc/en/Reference/Boolean) to make compound conditional statements.

Say, for example, that we want to turn on an LED when x is between -5 **AND** 5. We will use  "&&" operator:

```c++
void setup() {
  Serial.begin(9600);
}

void loop() {
  betweenFives(4);
  betweenFives(-10);
  betweenFives(6);
}

void betweenFives(int x) {
  if (x > -5 && x < 5) {
    Serial.println("between -5 and 5!");
  }
  else {
    Serial.println("not in the range")
  }
}
```

---

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
Building on the night light circuit, use the <a href="https://www.arduino.cc/en/Reference/Boolean">boolean operator "||" (OR)</a>
to turn on the nightlight if the light is close to its max or min readings. Otherwise,
turn off the night light. 
</pre>

---
