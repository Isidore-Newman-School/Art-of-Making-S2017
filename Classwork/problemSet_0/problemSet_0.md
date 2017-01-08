# Problem Set 0

Problem sets should be completed **individually**, but *if you have questions, don't hesitate to ask* for help. Problems sets are meant to cement your understanding of Arduino concepts.

**BEFORE BEGINNING ASSIGNMENT**

1. Copy the code [in this template](../templates/ps0_template.md) into a new Arduino project.
2. Put all problem set answers into this Arduino sketch
3. *To submit assignment*, email this fleshed-out template to Ms. deBB

---

## Variables

**(0)** What is the value of x after the loop() has run three times?

Hint 0: Don't be afraid to ask for help!  
Hint 1: Look up the following [compound operators](https://www.arduino.cc/en/Reference/HomePage):

* `++`
* `+=`
* `*=`

Hint 2: **To get partial credit**, put a comment next to each line of code with the value of x or y at that line.

```c++
/*
 * problemSet_0
 * Exercise 0
*/
int x = 4;

void setup() {
  int y = x;
  x = x * 4;
  x += y;
  x *= 1;
}

void loop() {
  x++;
}
```

## Built-in Functions

**(1)** Fill out the following table:

| Function | Pins used | Parameters? | Returns value? | Example of use |
| ------------- | ------------- | ----- | ----- | ----- |
| <a href="https://www.arduino.cc/en/Reference/DigitalWrite">digitalWrite()</a> | all analog and digital | (a)  | - | (b) |
| <a href="https://www.arduino.cc/en/Reference/analogWrite">analogWrite()</a> | (c) | (d) | - | (e) |
| <a href="https://www.arduino.cc/en/Reference/DigitalRead">digitalRead()</a> | all analog and digital | pin | HIGH/LOW | check button state |
| <a href="https://www.arduino.cc/en/Reference/AnalogRead">analogRead()</a> | (f) | (g) | (h) | read light sensor |

## Arguments and Parameters

**(2)** Setup the [RGB LED circuit](problemSet_0.md). Write a function, **siren()**, that alternates between red, blue, and off.
1. the function has a parameter, an integer, representing the time the red light stays on.
2. blue should stay on 500ms longer than red
3. the off state should last half as long as red

You may use any functions that we've defined in the classwork.

```c++
/*
 * problemSet_0
 * Exercise 2
 * siren()
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
  // call siren() here
}

// declare siren() here
```

## Returning Values
**(3)** Write a function, **fahren2Celsius()**, that:
1. has a parameter of data type *float* representing the temperature in Fahrenheit
2. *returns* the temperature in Celsius

Hint: the conversion equation is:
`Tc = (Tf - 32) / 1.8`

```c++
/*
 * problemSet_0
 * Exercise 3
 * fahren2Celsius()
*/

void setup() {
  Serial.begin(9600);

  float tempF = 88.7;

  Serial.print("The temperature ");
  Serial.print(tempF);
  Serial.print(" Fahrenheit is ");
  Serial.print(fahren2Celsius(tempF));
  Serial.println(" in Celsius");
}

void loop() { }

// declare fahren2Celsius() here
```
