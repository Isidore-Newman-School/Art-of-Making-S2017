## TODO

# 1. Variables

Topics
* [I. Our first variable](#i-what-is-Arduino)
* [II. Arithmetic with variables](#ii-arithmetic-with-variables)
* [III. Data Types](#iii-data-types)
* [IV. Operators](#iv-operators)

Exercises
* [Exercise 0. Blink Speed](#ex0)

---

## I. Our first variable
Variables in computer science allow us to store values. Variables help to make our code easier to change and easier to read. For example, we can replace the number 13 (representing pin 13) with the variable "ledPin":

```c++
int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  digitalWrite(ledPin, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);              // wait for a second
  digitalWrite(ledPin, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);              // wait for a second
}
```
---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
Create a new variable, delayTime, at the top of your sketch.
</pre>

---

## II. Arithmetic with variables


## III. Data Types
So far we've looked at one data type - 'int' - which stands for integers. In Arduino (and other programming languages) we have to specify what *type* of data we'll be storing. The Arduino reference
