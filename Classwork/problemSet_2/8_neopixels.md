# 8. Neopixels

## 0. Overview

|  | Topics | Exercises | Circuit |
| --- | --- | --- | --- |
| I | [Getting Started](i-getting-started) | - | - |
| II | [Basic Sketch](ii-basic-sketch) | [Exercise 0](#ex0) <br> [Exercise 1](#ex1) <br>[Exercise 2](#ex2) | Neopixel strip |

## I. Getting Started

![alt text](https://cdn-shop.adafruit.com/1200x900/1138-00.jpg)

[Neopixels](https://learn.adafruit.com/adafruit-neopixel-uberguide) are individually addressable, RGB LEDs. That means each LED in the strip can be its own color. RGB stands for red, green, blue. By selecting a value for each channel, we can create any color in the rainbow.

#### Library
The first step is to install the Neopixel Library from the Library Manager:

![alt text](http://codevista.net/wp-content/uploads/2015/08/Arduino-Library-Manager.png)

![alt text](images/manager.png)

#### Wiring
Plugging in Neopixels is pretty straightforward. Look closely at the strip.

1. The GND jumper must go to GND
2. 5V to 5V
3. middle pin (data) can go to any digital pin (most code uses pin 6)

#### Methods
A method in computer science is a function that belongs to a particular object, in this case, the "strip" object. The following methods can be used to control the pixels:
* **strip.setPixelColor**(pin, color)
* **strip.Color**(red, green, blue) - this function returns a color that can be used inside of strip.setPixelColor()
* **strip.clear**() - this function clears the colors (must be followed by strip.show())
* **strip.show**() - this function must be called after the pixel colors are set in order to see the changes
* **strip.setBrightness**() - sets the overall brightness of all the LEDs; takes a single argument, a number from 0 (off) to 255 (max brightness).

To get a particular color of the rainbow, set the correct RGB values. Check out [http://www.colorpicker.com/](http://www.colorpicker.com/) to get the RGB values of any color.

## II. Basic Sketch
Let's break down the contents of a simple Neopixel sketch. Every Neopixel sketch must include the library by including this file:

```c++
#include <Adafruit_NeoPixel.h>
```

Next we're going to define some values. `#define` is a useful component that allows the programmer to give a name to a constant value before the program is compiled. So every time the word `PIXEL_PIN` (below) shows up in the program, it will be replaced by the number 6.

This process is kind of like declaring variables (`int pixelPin = 6;`). It's probably a better process to stick with variable declaration, but be aware that `#define` accomplishes a similar objective and may be used in examples that we see moving forward. Here's the [reference page](https://www.arduino.cc/en/reference/define) if you're curious.

```c++
#define PIXEL_PIN    6   
#define PIXEL_COUNT  3
```

The next block of code defines which pin we're using to control the Neopixels and how many pixels are in our strip. We then initialize the "strip" (in other example files, it's called "pixels"; the name is irrelevant as long as we're consistent).

```c++
Adafruit_NeoPixel strip = Adafruit_NeoPixel(PIXEL_COUNT, PIXEL_PIN, NEO_GRB + NEO_KHZ800);
```

Next we have to begin the strip, and subsequently show it, in the setup():

```c++
void setup() {
  strip.begin();
  strip.show();
}
```

Finally, we're ready to set the pixel color in the draw() with the function. **NOTE** that you have to call `strip.show()` *after* you've set all of the pixel colors.

```c++
strip.setPixelColor( /* pixel # */ , strip.Color( /* red, green, blue */ ) ););
strip.setPixelColor( /* pixel # */ , strip.Color( /* red, green, blue */ ) ););
// etc.
strip.show();
```

Putting it all together, we can write a sketch that turns the first two pixels red:

```c++
#include <Adafruit_NeoPixel.h>   
#define PIXEL_PIN    6   
#define PIXEL_COUNT  7

Adafruit_NeoPixel strip = Adafruit_NeoPixel(PIXEL_COUNT, PIXEL_PIN, NEO_GRB + NEO_KHZ800);

void setup() {
  strip.begin();
  strip.show();
}

void loop() {
   strip.setPixelColor(0, strip.Color(255,0,0));
   strip.setPixelColor(1, strip.Color(255,0,0));
   strip.show();
}

```
---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
Set each LED in the strip to a different color of the rainbow.
</pre>

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
Write a function, setAllNeopixels(), that has three parameters - a red, green, and blue value (0-255).
The function uses a for loop to set every pixel to the colors passed as arguments when the function is called.

Use this function to flash Mardi Gras colors.
</pre>

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
Open the example file StrandTest (File > Examples > Adafruit Neopixel > strandtest).

1. How many different light functions are defined in the sketch?
2. What does the Wheel() function do?
3. What data type does Wheel() return?
</pre>
