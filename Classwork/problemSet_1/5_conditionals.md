# 5. Conditionals

Topics
* [I. if / else](#i-if--else)
* [II. if / else if / else](#ii-if--else-if--else)
* [III. Night Light](#iii-night-light)
* [IV. Booleans](#iv-booleans)

Exercises
* [Exercise 0](#ex0)
* [Exercise 1](#ex1)

---

## I. if / else
Conditional statements are used across all programming languages to add logic to code.

```c++
void setup() {
  Serial.begin(9600);
}

void loop() {
  checkIfPositive(-4);
  checkIfPositive(5);
}

void checkIfPositive(int x) {
  if (x > 0) {
    Serial.println("positive!");
  }
  else {
    Serial.println("not positive");
  }
}
```

## II. if / else if / else
Sometimes you want to test more than just 2 conditions. In these cases, you can use an arbitrary number of "else if" statements. Consider the previous example, on this time we want to check if x is positive, negative, or zero.

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


# III. Night Light

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
Our objective now is the create a night light. We want the LED to come on when the light in the room goes dim. Use the circuit from the previous chapter (below), and fill out the missing code in the following code block in order to create the night light:
</pre>

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

![alt text](http://s4a.cat/examples/photoresistor_led.png)


---

## IV. Booleans

So far we've exampled the following data types:
* int - integers
* float - floating point (decimal) numbers
* String - text

Booleans are another data type that store **true or false**.

```c++
boolean testing = true;

void setup() {
  Serial.begin(9600);
}

void loop() {
  // you can also just say, "if (testing) {"
  if (testing == true) {
    Serial.println("true!");
  }
  else {
    Serial.println("false!");
  }
}
```

---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
Use the circuit and the code you wrote in the previous exercise.

1. Add a boolean variable at the top of your sketch called "blinking"
2. Add the following logic:
  * If the night light is on and if blinking == true: blink the LED
  * If the night light is on and if blinking == false: just turn LED on
  * Otherwise, the night light / LED should be off
</pre>
