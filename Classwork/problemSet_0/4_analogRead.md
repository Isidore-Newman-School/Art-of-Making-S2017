# 4. analogRead()

Topics
* [I. Serial Monitor](#i-serial-monitor)
* [II. Analog Input Pins](#ii-analog-input-pins)
* [III. Strings](#iii-strings)
* [IV. Light Sensor](#iv-light-sensor)

Exercises
* [Exercise 0](#ex0)
* [Exercise 1](#ex1)
* [Exercise 2](#ex2)
* [Exercise 3](#ex3)

---

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

![alt text](serialmon.jpg)

---

## II. Strings
So far we've only looked at variables that are numbers- either integers of floats. We can also store text in variables (known as strings). String can be *concatenated* using the "+" operator.

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
What do the following lines of code print? What do you think is happening?
</pre>

```c++
void setup() {
  // tell the Arduino at what speed to communicate with computer
  Serial.begin(9600);

  String a = "7" + "3" + 2 + 1 + phrase;
  String b = 2 + 1 + "7" + "3" + phrase;
  String c = "7" + "3" + (2 + 1) + phrase;

  Serial.println(a);
  Serial.println(b);
  Serial.println(c);
}

void loop() {

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
Now we're going to read the value of a photoresistor or light sensor. You'll need:
* 10KΩ resistor
* photoresistor (light sensor)
* LED
* 3 jumper wires
* breadboard

Begin by setting up the following circuit:

![alt text](http://s4a.cat/examples/photoresistor_led.png)

In the code below, make note of a few things:
* We're using an *analog input pin* on the Arduino to read the sensor
* We declare `int lightPin = A0;` and declare the input in the setup(): `pinMode(lightPin, INPUT);`
* `analogRead(lightPin)` *returns* a value, so we can set a new variable, input, equal to the reading.

```c++
int ledPin = 13;
int lightPin = A0;  

void setup() {
  pinMode(ledPin, OUTPUT);
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
 How can we use the Serial Monitor to print:
 "The value of the photoresistor is: [insert reading here]"
</pre>
