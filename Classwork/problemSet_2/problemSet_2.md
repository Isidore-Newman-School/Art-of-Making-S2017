# Problem Set 2. Loops and Neopixels

Problem sets should be completed **individually**, but *if you have questions, don't hesitate to ask* for help. Problems sets are meant to cement your understanding of Arduino concepts.

**BEFORE BEGINNING ASSIGNMENT**

1. Copy the code [in this template](../templates/ps2_template.md) into a new Arduino project.
2. Put all problem set answers into this Arduino sketch
3. *To submit assignment*, email this fleshed-out template to Ms. deBB

---

**(0)** Write a function, **setColorWheel()**, that reads the value of a potentiometer (i.e. knob). The Neopixels start out red, but as the knob is turned, they become more and more green (and vice versa).

HINT: Use the Wheel() function.
HINT: Look up the [map()](https://www.arduino.cc/en/Reference/Map) function.

```c++
#include <Adafruit_NeoPixel.h>
#define POT_PIN   A0    
#define PIXEL_PIN    6   
#define PIXEL_COUNT  7

Adafruit_NeoPixel strip = Adafruit_NeoPixel(PIXEL_COUNT, PIXEL_PIN, NEO_GRB + NEO_KHZ800);

void setup() {
  pinMode(POT_PIN, INPUT);
  strip.begin();
  strip.show();
}

void loop() {
  setColorWheel();
}

void setColorWheel() {
  // your code here
}

// Adafruit - https://github.com/adafruit/Adafruit_NeoPixel/blob/master/examples/strandtest/strandtest.ino
// Input a value 0 to 255 to get a color value.
// The colours are a transition r - g - b - back to r.
uint32_t Wheel(byte WheelPos) {
  WheelPos = 255 - WheelPos;
  if(WheelPos < 85) {
    return strip.Color(255 - WheelPos * 3, 0, WheelPos * 3);
  }
  if(WheelPos < 170) {
    WheelPos -= 85;
    return strip.Color(0, WheelPos * 3, 255 - WheelPos * 3);
  }
  WheelPos -= 170;
  return strip.Color(WheelPos * 3, 255 - WheelPos * 3, 0);
}
```

**(1)** Write a function, pulseNeopixels(), that uses for loops and strip.setBrightness() to pulse the Neopixels (fading in and out).

**(2)** As long as a button is pressed, set a variable to a random number between 0-255. When the button is released, use the random number and the Wheel() function to set the Neopixels to that particular random color.

**(3)** In computer science the "%" (a.k.a. the modulo operator) is surprisingly useful. It is used to calculate the remainder after dividing two numbers. E.g.:

    5%2 = 1;
    4%2 = 0;
    3%2 = 1;
    2%2 = 0;
    1%2 = 1;
    0%2 = 0;

Use the modulo operator to write a function **fizzBarFuzz()** that uses a for loop and Serial.println() to print the numbers from 1 to 100, with two exceptions:

1. For numbers divisible by 3, print "Fizz" instead of the number
2. For numbers divisible by 5 (and not 3), print "Bar" instead.
3. For numbers divisible by 5 AND 3, print "Buzz" instead.

```c++
void setup() {
    pinMode(ledPin, OUTPUT);
    Serial.begin(9600);
    fizzBarFuzz();
}

void loop() {}

void fizzBarFuzz() {

}
```

**(4)** Write a new function, **slowClap()** that uses a [for loop](https://www.arduino.cc/en/Reference/For) and the **onOff()** function. Each time through the loop the LED should should blink 3 times, and with each iteration the LED should blink noticeably faster. Do 10 iterations.
