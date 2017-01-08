# 1. Variables

## 0. Overview

| Topics | Exercises | Circuit |
| --- | --- | --- | --- |
| [I. Our first variable](#i-what-is-Arduino) | [Exercise 0](#ex0) | Blinking LED |
| [II. Arithmetic with variables](#ii-arithmetic-with-variables) | [Exercise 1](#ex1) | - |
| [III. Data Types](#iii-data-types) | - | - |
| [IV. Operators](#iv-operators) | [Exercise 2](#ex2) | - |


## I. Our first variable
Setup the following circuit with the LED's long leg plugged into pin 13 and the short led into ground (GND):

| Circuit | Materials | Diagram |
| --- | --- | --- |
| blinking LED | <ul><li>Arduino</li><li>USB cord</li><li>LED</li></ul> | ![alt text](../images/ledpin13.jpg) |


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
Create a new variable, delayTime, at the top of your sketch. Use this variable
in the blink sketch to control the delay time between turning on/off.
</pre>

---

## II. Arithmetic with variables

When we define functions, we can do arithmetic on the variables. Consider the following example:

```c++
int ledPin = 13;
int x = 500;
int y = 100;

void setup() {
  pinMode(ledPin, OUTPUT);
  delay(x * 2 + y);         // delays 1100 milliseconds
  x = y;                    // x is assigned the value of y = 100
  y = 300;
  delay(x);                 // delays 100 milliseconds
  delay(y);                 // delays 300 milliseconds
}

void loop() {
  digitalWrite(ledPin, HIGH);
}
```

---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
1. Using a single variable, <b>delayTime</b>, make the LED blink like a heartbeat:
short, long, short, long, etc.
2. The first beat should delay as long as the variable delayTime.
3. The second pulse should delay <b>twice as long</b> as the first, regardless of the
value of delayTime.
</pre>

```c++
// your variable here
int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // heartbeat code goes here
}
```

---


## III. Data Types
So far we've looked at one data type - 'int' - which stands for integers. In Arduino (and other programming languages) we have to specify what *type* of data we'll be storing. The [Arduino reference](https://www.arduino.cc/en/Reference/HomePage) lists quite a few different data types under "Variables." We're going to focus on just a few types in the beginning:

```c++
int var1 = 10;          // integers
float var2 = 10.42;     // floats, or floating-point (i.e. decimals) numbers
String name = "Jenna";  // strings, or text
boolean test = true;    // booleans are true or false
```

## IV. Variable Scope
In programming we refer to two types of variables:
1. **global** - variables that can be seen by every function in a program
2. **local** - variables only visible to the function in which they are declared

When we declare functions *at the top of a sketch, the variables are global* and can be used any where in the sketch. Once a global variable is declared with a data type, you no longer need to specify the data type.

---

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
1. In the following example, which variable(s) are global? Local?

2. Refer to the code below and choose the correction option:
  1. only `delay(y)` is correct
  2. only `delay(x)` and `delay(y)` are correct
  3. all delays work  
</pre>

```c++
int ledPin = 13;
int z = 50;

void setup() {
  pinMode(ledPin, OUTPUT);
  int x = 100;
  z = x + 200;
}

void loop() {
  int y = 500;
  delay(x);             
  delay(y);    
  delay(z);         
}
```
