# Problem Set 2 Template

Copy the code below into a new Arduino sketch. Save your problem set in this format and email Ms. deBB this file to submit the assignment.

You can comment/ uncomment certain sections to test code by highlighting the area in question and pressing `CTRL + /` or `COMMAND + /`.

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
  // EXERCISE 0
  // setColorWheel()

  // EXERCISE 1
  // pulseNeopixels()

  // EXERCISE 2
  // setRandomColor()

  // EXERCISE 3
  // fizzBarFuzz()

  // EXERCISE 4
  // slowClap()
}

// EXERCISE 0
// setColorWheel()

// EXERCISE 1
// pulseNeopixels()

// EXERCISE 2
// setRandomColor()

// EXERCISE 3
// fizzBarFuzz()

// EXERCISE 4
// slowClap()

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
