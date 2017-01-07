Arrays are ways to a collection of variables.

### Declaring Arrays
```c++
int myPins[] = {2, 4, 8, 3, 6};
```


### Accessing Elements
The values in arrays are accessed using an index, beginning with zero. E.g.:
```c++
int delayTimes[] = {200, 400, 85, 390, 610};
// delayTimes[0] is 2
// delayTimes[1] is 4
// ...
// delayTimes[4] is 6
int totalTime = delayTimes[0] + delayTimes[1];  // 600
```

To assign elements in an array to a value:
```c++
delayTimes[1] = 1000;
```

### Arrays with For Loops
```c++
for (int i = 0; i < 5; i++) {
  Serial.println(myPins[i]);
}
```



```c++
// notes to play, corresponding to the 3 sensors:
int notes[] = {500, 300, 200};

void setup() {
    tone(8, notes[0], 500);
    delay(100);
    tone(8, notes[1], 500);
    delay(100);
    tone(8, notes[2], 500);
    delay(100);
}

void loop() {
  // no need to repeat the melody.
}
```

**Exercise**
Put the first 7 notes of "Mary Had a Little Lamb" in an array called notes[]. Use a for loop and tone() to play the notes of the array in order.


**(2)**
What does sum equal?

```c++
int lotteryTicket[] = { 40, 23, 11, 12, 52};
int sum = lotteryTicket[0] + lotteryTicket[3];
```

**(3)** Create two arrays:
1. an array of 5 elements called lightLevels[] with numbers between 0 and 255.
2. an array called durations[] with 5 numbers between 100 and 1000.  

Use a for loop to cycle through the elements of the arrays. Use **analogWrite()** to turn on an LED at the brightness level in the lightLevels[] array and keep it on for the amount of time in the durations[] array.


Strings can also be represented as arrays of characters ("char" data type). For example:

```c++
// all of these are valid:
char myString[] = "arduino";
// char myString[8] =  "arduino";
// char myString[] = {'a', 'r', 'd', 'u', 'i', 'n', 'o'};
// char myString[8] = {'a', 'r', 'd', 'u', 'i', 'n', 'o'};
// char myString[8] = {'a', 'r', 'd', 'u', 'i', 'n', 'o', '\0'};

void setup(){
  Serial.begin(9600);
}

void loop(){
for (int i = 0; i < 7; i++){
   Serial.println(myString[i]);
   delay(500);
   }
}

```

**(3)** The **sosPulses[]** array stores the morse code pulses of the SOS signal. Use a for loop and a conditional statement to make an LED blink the SOS signal in accordance with [International Morse Code Rules](http://morsecode.scphillips.com/morse2.html):

* dot = one unit
* dash = three units
* space between the components of one character is one unit
* space between characters is three units



```c++
char sosPulse[21] = ". . .   - - -   . . .";

void setup(){
  Serial.begin(9600);
}

void loop(){
  // turn LED on
}

```

#5. Neopixels

![alt text](https://cdn-shop.adafruit.com/1200x900/1138-00.jpg)

[Neopixels](https://learn.adafruit.com/adafruit-neopixel-uberguide) are individually addressable, RGB LEDs. That means each LED in the strip can be its own color. RGB stands for red, green, blue. By selecting a value for each channel, we can create any color in the rainbow.

## Install Library
The first step is to install the Neopixel Library from the Library Manager:

![alt text](http://codevista.net/wp-content/uploads/2015/08/Arduino-Library-Manager.png)

![alt text](images/manager.png)

## Wiring
Plugging in Neopixels is pretty straigtforward. Look closely at the strip. The GND jumper must go to GND, 5V to 5V, and the middle pin (data) can go to any digital pin. Most code uses pin 6.

## Bare Minimum Neopixel Sketch
Every Neopixel sketch must include the library by including this file:
```c++
#include <Adafruit_NeoPixel.h>
```

This next block of code defines which pin we're using to control the Neopixels and how many pixels are in our strip. We then initialize the "strip" (in other example files, it's called "pixels"; the name is irrelevant as long as we're consistent).

```c++
#define PIXEL_PIN    6   
#define PIXEL_COUNT  3

Adafruit_NeoPixel strip = Adafruit_NeoPixel(PIXEL_COUNT, PIXEL_PIN, NEO_GRB + NEO_KHZ800);
```

Next we have to begin the strip in the setup():

```c++
void setup() {
  strip.begin();
  strip.show();
}
```

Finally, we're ready to set the pixel color in the draw() with the function:

```c++
strip.setPixelColor( /* pixel # */ , strip.Color( /* red, green, blue */ ) ););
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

The following functions can be used to control the pixels:
* **strip.setPixelColor**(pin, color)
* **strip.Color**(red, green, blue) - this function returns a color that can be used inside of strip.setPixelColor()
* **strip.clear**() - this function clears the colors (must be followed by strip.show())
* **strip.show**() - this function must be called after the pixel colors are set in order to see the changes
* **strip.setBrightness**() - sets the overall brightness of all the LEDs; takes a single argument, a number from 0 (off) to 255 (max brightness).

To get a particular color of the rainbow, set the correct RGB values. Check out [http://www.colorpicker.com/](http://www.colorpicker.com/) to get the RGB values of any color:

![alt text](images/colorpicker.png)

**Exercise**
**(1)** Set each LED to a different color of the rainbow.

**(2)** How do we turn the Neopixels off? Make the Neopixels blink.

**(3)** Open the example file StrandTest (File > Examples > Adafruit Neopixel > strandtest). What do each of the functions do?

**(4)** Make the Neopixels fade in and out using a for loop and the setBrightness() function.
