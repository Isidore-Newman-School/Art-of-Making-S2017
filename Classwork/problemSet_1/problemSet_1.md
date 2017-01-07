<!-- # Problem Set 1. conditionals

## Review


// two buttons
// if press number one, light goes on and stays on
// if press number two, light goes off and stays off

2) Fill out the following function, **checkLightSensor()** so that if:
* light is less than 300, turn LED off.
* light is less than 400, turn LED 10% on.
* light is less than 500, turn LED 50% on.
* light is over 500, turn LED 100% on.

```c++
int ledPin = 9;
int piezoPin = A0;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(piezoPin, INPUT);
}

void draw() {
  checkLightSensor();
}

void checkLightSensor() {
  // your code here
}
``` -->
