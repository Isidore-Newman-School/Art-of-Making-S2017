# Problem Set 1 Template

Copy the code below into a new Arduino sketch. Save your problem set in this format and email Ms. deBB this file to submit the assignment.

You can comment/ uncomment certain sections to test code by highlighting the area in question and pressing `CTRL + /` or `COMMAND + /`.

```c++
// int ledPin = 9;      // Exercise 0
// int ledPin = 13;     // Exercises 1 & 2
int buttonPin1 = 2;  
int buttonPin2 = 3;

// any other variables go here

void setup() {
    pinMode(ledPin, OUTPUT);
    pinMode(buttonPin1, INPUT);
    pinMode(buttonPin2, INPUT);   
}

void loop() {
  // Exercise 0
  // checkPot();

  // Exercise 1
  // checkTwoButtons();

  // Exercise 2
  // ledMode();
}

// Exercise 0
void checkPot() {
  // your code here
}

// Exercise 1
void checkTwoButtons() {
  // your code here
}

// Exercise 2
void ledMode() {
  // your code here
}

void blinky() {
  digitalWrite(ledPin, HIGH);
  delay(1000);
  digitalWrite(ledPin, LOW);
  delay(1000);
}
```
