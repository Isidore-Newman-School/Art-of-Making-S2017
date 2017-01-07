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

**(4)** Write some code that turns all of the Neopixels blue when you press a button. Otherwise, it turns them all off.

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
  if ( // button is pressed?  ) {
    // turn all Neopixels on
  }
  else {
    // turn all Neopixels off
  }
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

## for loop
To make the LED fade in and out, we'll use a control structure known as a [**for** loop](https://www.arduino.cc/en/Reference/For). For loops help us iterate/ repeat for a certain number of cycles.

![alt text](https://www.arduino.cc/en/uploads/Reference/ForLoopIllustrated.png)


To fade in and out:

```c++

int ledPin = 11;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  fadeIn();
  fadeOut();
}

void fadeIn() {
    for (int i = 0; i < 255; i++) {
    analogWrite(ledPin, i);
    delay(10);
  }
}

void fadeOut() {
    for (int i = 255; i > 0; i--) {
    analogWrite(ledPin, i);
    delay(10);
  }
}
```
