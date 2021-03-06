# 4. analogRead()

## 0. Overview

|  | Topics | Exercises | Circuit |
| --- | --- | --- | --- |
| I | [Serial Monitor](#i-serial-monitor) | [Exercise 0](#ex0) | - |
| II | [Analog Input Pins](#ii-analog-input-pins)| [Exercise 1](#ex1) | - |
| III | [Strings](#iii-strings)| [Exercise 2](#ex2) | - |
| IV | [Light Sensor](#iv-light-sensor) | [Exercise 3](#ex3) | light sensor |

## I. Serial Monitor
In this section we're going to be *reading* the value of sensors. But before we do, we need some way to get values off of the Arduino and onto our computer to make sure our sensors are working. This is where the Serial Monitor comes in! Add the following line of code to your setup():

```c++
void setup() {
  // tell the Arduino at what speed to communicate with computer
  Serial.begin(9600);
}
```

Now we can print values to the screen with **Serial.print()** and **Serial.println()**.

```c++
void setup() {
  // tell the Arduino at what speed to communicate with computer
  Serial.begin(9600);
}

void loop() {
  Serial.print("Let's print some values like, ");
  Serial.print(100 + 33);
  Serial.println(", to the Serial Monitor!");   
}
```

---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
Upload the previous code and open the Serial Monitor on your computer to see
values printed to the screen. Make sure the baud rate of the Serial Monitor
is set to 9600.

Experiment with Serial.print() and Serial.println(). What is the difference
between these functions?
</pre>

![alt text](../images/serialmon.jpg)

---

## II. Strings
So far we've only looked at variables that are numbers- either integers of floats. We can also store text in variables (known as strings). String can be *concatenated* using the "+" operator.

```c++
void setup() {
  // tell the Arduino at what speed to communicate with computer
  Serial.begin(9600);
}

void loop() {
  String a = "hello ";
  String b = a + "world!";
  String c = b + 123;

  Serial.println(a);
  Serial.println(b);
  Serial.println(c);
}
```

---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
The example below attempts to concatenate a string with a number and print with the result, but it doesn't compile. Read the <a href="https://www.arduino.cc/en/Tutorial/StringAdditionOperator"String concatenation page</a> to see if you can figure out why.
</pre>

```c++
void setup() {
  // tell the Arduino at what speed to communicate with computer
  Serial.begin(9600);
}

void loop() {
  String a = "hello " + "world!" + 123;
  Serial.println(a);
}
```

---

## III. Analog Input Pins
So far we've looked at two functions for *writing*, or setting voltages:
* digitalWrite([pin], [HIGH/LOW])
* analogWrite([pin], [0-255])

We're going to use a new function, [analogRead()](https://www.arduino.cc/en/Reference/AnalogRead), to get a value of sensors. analogRead():
* uses "analog input" pins only
* takes a pin number as an argument
* *returns* a number between 0 and 1023- representing 0 to 5 volts.

---

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
 Look at your Arduino. How many analog input pins are there?
</pre>

---

## IV. Light Sensor
Now we're going to read the value of a photoresistor (or light sensor). Begin by setting up the following circuit:

| Circuit | Materials | Diagram |
| --- | --- | --- |
| light sensor | <ul><li>photoresistor (light sensor)</li><li>3 jumpers wires</li><li>10KΩ resistor</li><li>breadboard</li></ul> | ![photoresistor arduino](../images/photo.png) |


In the code below, make note of a few things:
* We're using an *analog input pin* on the Arduino to read the sensor
* We declare `int lightPin = A0;` and declare the input in the setup(): `pinMode(lightPin, INPUT);`
* `analogRead(lightPin)` *returns* a value, so we can set a new variable, input, equal to the reading.

```c++
int lightPin = A0;  

void setup() {
  pinMode(lightPin, INPUT);   // notice this pin is an INPUT
}

void loop() {
  int input = analogRead(lightPin);
}
```

---

<a name="ex3"></a>
<pre>
<b>Exercise 3:</b>
 Building on the code above, how can we use the Serial Monitor to print:
 "The value of the photoresistor is: [insert reading here]"
</pre>
