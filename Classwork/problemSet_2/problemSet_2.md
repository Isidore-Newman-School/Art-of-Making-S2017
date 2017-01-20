To be completed...
<!-- # Problem Set 1. conditionals

Problem sets should be completed **individually**, but *if you have questions, don't hesitate to ask* for help. Problems sets are meant to cement your understanding of Arduino concepts.

**BEFORE BEGINNING ASSIGNMENT**

1. Copy the code [in this template](../templates/ps2_template.md) into a new Arduino project.
2. Put all problem set answers into this Arduino sketch
3. *To submit assignment*, email this fleshed-out template to Ms. deBB

---

**(0)** Write a function, **setAllColor()**, that *uses a for loop* to turn all of the Neopixels in a strip to a particular color. The function has three parameters- one for red, green, and blue.

```c++
#include <Adafruit_NeoPixel.h>
#define BUTTON_PIN   2    
#define PIXEL_PIN    6   
#define PIXEL_COUNT  7

Adafruit_NeoPixel strip = Adafruit_NeoPixel(PIXEL_COUNT, PIXEL_PIN, NEO_GRB + NEO_KHZ800);

void setup() {
  pinMode(BUTTON_PIN, INPUT);
  strip.begin();
  strip.show();
}

void loop() {
  setAllColor(0, 255, 0);   // sets all the Neopixels green
  setAllColor(0, 0, 255);   // sets all the Neopixels blue
}

void setAllColor() {
  // your code here
}
```

**(1)** As long as (while) a button is pressed, set a variable to a random number between 0-255

* Hint: Use the Wheel() function to get a color. Pass Wheel() a value between 0-255 to get all the colors of the rainbow.

**(2)** In computer science the "%" (a.k.a. the modulo operator) is surprisingly useful. It is used to calculate the remainder after dividing two numbers. E.g.:

    5%2 = 1;
    4%2 = 0;
    3%2 = 1;
    2%2 = 0;
    1%2 = 1;
    0%2 = 0;

Use the modulo operator to write a function **fizzBuzz()** that uses a for loop and Serial.println() to print the numbers from 1 to 100, with two exceptions:

1. For numbers divisible by 3, print "Fizz" instead of the number
2. For numbers divisible by 5 (and not 3), print "Buzz" instead.

```c++
void setup() {
    pinMode(ledPin, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    fizzBuzz();
}

void fizzBuzz() {

}
``` -->

1) Use a for loop to stay on for an increasing number of seconds: 1 second, 2 seconds, 3 seconds, ... , 10 seconds.

```c++
int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  delayIncrease();
}

void delayIncrease() {

  // fill this out

  for (int i =       ; i            ; i++) {

    digitalWrite(ledPin, HIGH);

    // fill this out

    delay(           );

    digitalWrite(ledPin, LOW);
    delay(1000);
  }
}
```

2) Write a function **printRange()** that takes two arguments- start and end- and uses a for loop to print out all of the numbers between the start and end.

```c++
void setup() {
  Serial.begin(9600);
}

void loop() {
  printRange(3, 6);  // prints: 3, 4, 5
  printRange(1, 5);  // prints: 1, 2, 3, 4
}

void printRange(int start, int end) {











}
```

**(3)** Write a new function, **slowClap()** that uses a [for loop](https://www.arduino.cc/en/Reference/For) and the **onOff()** function. Each time through the loop the LED should should blink 3 times, and with each iteration the LED should blink noticeably faster. Do 10 iterations.




**(3)** Write a new function, **slowClap()** that uses a [for loop](https://www.arduino.cc/en/Reference/For) and the **onOff()** function. Each time through the loop the LED should should blink 3 times, and with each iteration the LED should blink noticeably faster. Do 10 iterations.

**(0)** Write a function **testHearing()** that uses a for loop to play the frequencies from 100 to 10000 on a speaker. Delay for one millisecond for each frequency.

```c++
void loop() {
  testHearing();
}

void testHearing() {
  // your code here
  // tone(pin, note, duration);
}
```



1) Use a for loop to stay on for an increasing number of seconds: 1 second, 2 seconds, 3 seconds, ... , 10 seconds.


```c++
int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  delayIncrease();
}

void delayIncrease() {

  // fill this out

  for (int i =       ; i            ; i++) {

    digitalWrite(ledPin, HIGH);

    // fill this out

    delay(           );

    digitalWrite(ledPin, LOW);
    delay(1000);
  }
}
```

2) Write a function **printRange()** that takes two arguments- start and end- and uses a for loop to print out all of the numbers between the start and end.

```c++
void setup() {
  Serial.begin(9600);
}

void loop() {
  printRange(3, 6);  // prints: 3, 4, 5
  printRange(1, 5);  // prints: 1, 2, 3, 4
}

void printRange(int start, int end) {
}
```




**(1)** In computer science the "%" (a.k.a. the modulo operator) is surprisingly useful. It is used to calculate the remainder after dividing two numbers. E.g.:

    5%2 = 1;
    4%2 = 0;
    3%2 = 1;
    2%2 = 0;
    1%2 = 1;
    0%2 = 0;

Use the modulo operator to write a function **fizzBuzz()** that uses Serial.print() to print the numbers from 1 to 100, with two exceptions:

1. For numbers divisible by 3, print "Fizz" instead of the number
2. For numbers divisible by 5 (and not 3), print "Buzz" instead.

```c++
void setup() {
    pinMode(ledPin, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    fizzBuzz();
}

void fizzBuzz() {

}
```
