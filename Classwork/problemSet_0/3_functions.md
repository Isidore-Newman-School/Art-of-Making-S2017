# 3. Functions

## 0. Overview

|  | Topics | Exercises | Circuit |
| --- | --- | --- | --- |
| I | [Defining Functions](#i-defining-functions) | [Exercise 0](#ex0) | RGB LED |
| II | [Parameters and Arguments](#ii-parameters-and-arguments)| [Exercise 1](#ex1) | RGB LED |
| III | [Multiple Arguments](#iii-multiple-arguments)| [Exercise 2](#ex2) | RGB LED |
| IV | [Returning Values](#iv-returning-values)| [Exercise 3](#ex3) | RGB LED |

## I. Defining Functions

Arduino comes with many built-in functions that you can explore in the [reference](https://www.arduino.cc/en/Reference/). In addition to using these functions, we can also write our own. We're going to continue using the RGB LED circuit from the previous chapter.

| Circuit | Materials | Diagram |
| --- | --- | --- |
| RGB LED | <ul><li>4 jumpers</li><li>3, 220Ω resistors</li><li>RGB LED</li><li>breadboard</li></ul> | ![alt text](../images/rgb.jpg) |

Let's write a function, **greenLight()**, that sets the LED to green.

1. We begin by **declaring our own function, "void greenLight() {"**:

2. Next we **call our function** using the function name followed by parentheses. The function will not be called by default; we have to call it in the setup() or loop():

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
  greenLight();
}

void greenLight() {
  // makes the color green
  analogWrite(redPin, 0);
  analogWrite(greenPin, 255);
  analogWrite(bluePin, 0);  
}
```

**NOTE: Why functions?**
Functions make our code easier to read and helps to avoid code repetition.

---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
1. Using the RGB LED circuit, write a function, <b>whiteLight()</b> that makes the LED white.

2. Alternate between green and white light in the loop.
</pre>

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
  // call functions here
}

void greenLight() {
  // makes the color green
  analogWrite(redPin, 0);
  analogWrite(greenPin, 255);
  analogWrite(bluePin, 0);  
}

// declare whiteLight() here

```

---

## II. Parameters and Arguments
Parameters in functions allows us reuse the code of a function but pass in different values.

For example, let's write a function, **goGreenies()**, that flashes between white and green light. The function has a parameter - flashTime - that determines how fast the colors flash.

```c++
/*
 * Example of function arguments/parameters
 * goGreenies()
*/

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
  // call function with argument
  goGreenies(100);
  goGreenies(500);
  goGreenies(1000);
}

// declare function with parameter
void goGreenies(int flashTime) {  
  greenLight();
  delay(flashTime);
  whiteLight();
  delay(flashTime);
}

// greenLight() goes here
// defined in previous exercise

// whiteLight() goes here
// declared in previous exercise
```

---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
Write a function <b>blueBrightness()</b> that has a single parameter- representing the brightness
of the blue LED- and sets the RGB LED accordingly.

Call your function several times in the loop() with increasing blue brightness values
(and make sure to put delays in between).
</pre>

---

#### Recap
* A **parameter** is a variable in a function definition.
  * *flashTime is the parameter* in the previous example.
* An **argument** is the data you pass into the method's parameters.
  * *100, 500, and 1000 are the arguments* in the previous example

## III. Multiple Arguments

To pass multiple arguments, we separate the parameters with commas.

As an example, let's write a function, **setLedColor()**, for the RGB LED that has three parameters- one for the red value, green value, and blue value of the LED. Then the function sets the LED colors according to the arguments passed to the function.

```c++
/*
 * Example of multiple function arguments/parameters
 * setLedColor()
*/

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
  setLedColor(0, 0, 255);  // blue
}

// declare function with multiple parameters
void setLedColor(int redC, int greenC, int blueC) {
  analogWrite(redPin, redC);
  analogWrite(greenPin, greenC);
  analogWrite(bluePin, blueC);  
}
```

---

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
Write a function <b>stopLight()</b> that cycles through the stop light colors.
The function takes three arguments:

1. delay of the green light
2. delay of the yellow light
3. delay of red light

Call your function several times in the loop() with various delay values.
</pre>

```c++
/*
 * Exercise of multiple function parameters/ arguments
 * stopLight()
*/

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
  // call your function here

}

// declare stopLight() here


void setLedColor(int redC, int greenC, int blueC) {
  analogWrite(redPin, redC);
  analogWrite(greenPin, greenC);
  analogWrite(bluePin, blueC);  
}
```

---

## IV. Returning Values

So far we've only looked at functions that are "void." These functions execute code, but they do not *return* values. Now we're going to look at functions that do a calculation and *return* a value.

**Step 1.** Begin your function declaration *with the data type* that your function will return. For example, to declare the function sum() returns the sum (an integer), we *start the function declaration with* `int`:

```c++
int sum(int a, int b) {
  ...
}
```
**Step 2.** Use *return* keyword when you have a value that you'd like the function to return.

```c++
int sum(int a, int b) {
  return a + b;
}
```

**Step 3.** When we call sum(), we can set a variable equal to the function sum() because it returns a value:

```c++
/*
  * Example of returning values
  * sum()
*/

int redPin = 11;
int greenPin = 10;
int bluePin = 9;

void setup() {
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);  
}

void loop() {
  int delay1 = sum(250, 250);            // = 500
  int delay2 = sum(delay1, delay1);      // = 1000

  setLedColor(0, 255, 0);
  delay(delay1);
  setLedColor(0, 0, 0);
  delay(delay2);
}

// Sum returns an integer
int sum(int a, int b) {
  return a + b;
}

void setLedColor(int redC, int greenC, int blueC) {
  analogWrite(redPin, redC);
  analogWrite(greenPin, greenC);
  analogWrite(bluePin, blueC);  
}
```

---

<a name="ex3"></a>
<pre>
<b>Exercise 3:</b>
 Write a function, square(), that takes a single argument-
 <b>a float</b> and returns the square of that number- <b>also a float</b>.
</pre>

```c++
/*
  * Exercise of returning values
  * square()
*/
int redPin = 11;
int greenPin = 10;
int bluePin = 9;

void setup() {
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);  
}

void loop() {
  float f1 = square(10.6);
  float f2 = square(5.5);
}

// square function goes here
```
