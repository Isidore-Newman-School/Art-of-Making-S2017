# Functions

Topics
* [I. Defining Functions](#i-defining-functions)
* [II. Arguments](#ii-arguments)
* [III. Returning Values](#iii-returning-values)

Exercises
* [Exercise 0](#ex0)
* [Exercise 1](#ex1)
* [Exercise 2](#ex2)

---

## I. Defining Functions

Arduino comes with many built-in functions that you can explore in the [reference](https://www.arduino.cc/en/Reference/). In addition to using these functions, we can also write our own.

We're going to continue using the [RGB LED circuit](#ii-rgb-leds) from the previous chapter. Let's write a function, **goGreenies()**, that sets the LED to green.

1. We begin by **declaring our own function, "void goGreenies() {"**:

2. Next we **call our function** using the function name followed by parentheses. The function will not be called by default; we have to call it in the setup() or loop():

```c++
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
    blinky();      // calling function here
}

// function definition here
void blinky() {
    digitalWrite(ledPin, HIGH);   
    delay(1000);                  
    digitalWrite(ledPin, LOW);    
    delay(1000);                  
}
```

#### Why functions?
Functions make our code easier to read and helps to avoid code repetition.

---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
1. Using the code you wrote in Exercise 1, create a function, <b>lightStep()</b>,
that lights up an LED in steps of increasing brightness.

2. Alternate between delaying 1 second and 1/2 second between calling lightStep().
</pre>


```c++
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // calling function here
}

// declare your function here
```

---

## II. Arguments
Passing arguments to functions allows us reuse the code of a function but pass in different values. As an example, instead of delaying 1 second every time we call blink(), let's pass an argument to blink() so that we can set the delay to any arbitrary value.

**Step 1:** When we declare the function, we include *parameters* inside of the parentheses of the function header. A parameter tells our function what *type* of data the function should expect. Inside of our function definition we refer to the parameter:

**Step 2:** When we call our function, we pass an *argument* - in this case, a number representing the delay time.

```c++
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // call blink with arguments

  blinky(500);     // 500 is an argument
  blinky(800);     // 800 is an argument
  blinky(200);     // 200 is an argument
}

// delayTime is a parameter
void blinky(int delayTime) {
    digitalWrite(ledPin, HIGH);   
    delay(delayTime);                  
    digitalWrite(ledPin, LOW);    
    delay(delayTime);                                 
}
```

NOTE:
* A **parameter** is a variable in a function definition.
* An **argument** is the data you pass into the method's parameters.


#### Multiple Arguments

To pass multiple arguments, we separate the parameters with commas. For example, to write a blinky() function that has a parameter for the first *and* second delay time:

```c++
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  blinky(500, 1000);     // pass two arguments
}

// delayTime is a parameter
void blinky(int delayTime1, int delayTime2) {
    digitalWrite(ledPin, HIGH);   
    delay(delayTime1);                  
    digitalWrite(ledPin, LOW);    
    delay(delayTime2);                                 
}
```
---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
Write a function <b>setBrightness()</b> that takes two arguments:

1. The first is an integer between 0 and 255.
It sets the LED to a level of brightness between 255 (max on) to 0 (off).

2. The second integer sets the amount of time the LED delays at that brightness.

Call your function several times in the loop() with various values for brightness and delay.
</pre>

```c++
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // call your function
}

// define setBrightness() here
```


## III. Returning Values

So far we've only looked at functions that are "void." These functions execute code, but they do not *return* values. Now we're going to look at functions that do a calculation and *return* a value.

**Step 1.** Declare your function *with the data type* that your function will return. For example, to declare the function sum() that takes two values and returns their sum (an integer):

```c++
int sum(int a, int b) {
  return a + b;
}
```

**Step 2.** When we call sum(), we can set a variable equal to the function sum() because it returns a value:

```c++
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {

  int s1 = sum(500, 500);
  int s2 = sum(250, 250);

  digitalWrite(ledPin, HIGH);
  delay(s1);
  digitalWrite(ledPin, LOW);
  delay(s2);
}

int sum(int a, int b) {
  return a + b;
}
```

---

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
 Write a function, square(), that takes a single argument-
 <b>a float</b> and returns the square of that number- <b>also a float</b>.
</pre>

```c++
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {

  digitalWrite(ledPin, HIGH);
  delay(square(10, 10));
  digitalWrite(ledPin, LOW);
  delay(square(20, 20));
}

// square function goes here
```
