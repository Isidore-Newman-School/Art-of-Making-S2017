# 9. Arrays

## 0. Overview

|  | Topics | Exercises | Circuit |
| --- | --- | --- | --- |
| I | [Declaring Arrays](i-declaring-arrays) | - | - |
| II | [Accessing Arrays](ii-accessing-arrays) | [Exercise 0](#ex0) <br> [Exercise 1](#ex1) | Neopixel strip |
| III | [Arrays with For Loops](iii-arrays-with-for-loops) | |
| IV | [Aggregation](iv-aggregation) | |
| V | [Strings](v-strings) | |

---

## I. Declaring Arrays
Think of arrays as an ordered list of values (numbers, strings, etc.). You can declare arrays with or without initializing the values. All of the following are valid:

```c++
int myValues[] = {2, 4, 8, -3, 6};
int myValues[5];
int myValues[5] = {2, 4, 8, -3, 6};
```

## II. Accessing Arrays
We use an index- the value between "[]" - to access the values in the array. Index values start at 0. To access the first and third items in the myValues[] array:

```c++
int myValues[] = {2, 4, 8, -3, 6};
int val1 = myValues[0];   // equals 2
int val2 = myValues[2];   // equals 8
```

We can also use the index to set values of the array.

**NOTE** in the example below that we declare the array with 3 (the number of items in the array), but since we start counting at 0, the last item in the array is accessed with `myArray[2]`.

```c++
int myArray[3];

void setup()  {
  myArray[0] = 10;
  myArray[1] = -2;
  myArray[2] = 4;
}
```

---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
After the loop has run one time, what is the value of <em>num</em> in the code below ?
</pre>

```c++
int myArray[] = {100, 25, 30, 1, 90};

void setup() {
  myArray[2] = 60;
}

void loop() {
  myArray[3]--;
  int num = myArray[3] - myArray[0] + myArray[2];
}
```

---

Let's create an array of delay times and blink an LED for each of the delay times in the array:

```c++
int delayTimes[] = {1000, 500, 200, 600};
int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  blinky(delayTimes[0]);
  blinky(delayTimes[1]);
  blinky(delayTimes[2]);
  blinky(delayTimes[3]);
}

void blinky(delayT) {
  digitalWrite(ledPin, HIGH);
  delay(delayT);
  digitalWrite(ledPin, LOW);
  delay(delayT);
}
```

---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
Create a new array- delayHalfTimes[]. The values in this array should be half of the time
in the delayTimes[] array, <em>for any arbitrary set of values in the delayTimes[] array</em>.

Call blinky() with the values in this new array.
</pre>

---

## III. Arrays with For Loops

Frequently we use for loops to quickly access values in an array. For example, we can simplify the previous example with a for loop:

```c++
int delayTimes[] = {1000, 500, 200, 600};
int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  for (int i = 0; i < 4; i++) {
    blinky(delayTimes[i]);
  }
}

void blinky(delayT) {
  digitalWrite(ledPin, HIGH);
  delay(delayT);
  digitalWrite(ledPin, LOW);
  delay(delayT);
}
```

---

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
Setup a circuit with a speaker. How can we use a for loop to simplify the code below and play all
of the notes in the notes[] array?
</pre>

---

```c++
// notes to play, corresponding to the 3 sensors:
int notes[] = {523, 784, 200};

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

---

<a name="ex3"></a>
<pre>
<b>Exercise 3:</b>
Add an array called noteDurations[] with numbers between 100 and 4000. These numbers represent the
amount of time that each note in the notes[] array should play.

Change the notes[] array and use noteDurations[] to play the tune of, "Here comes the bride"
(half note, dotted quarter note, eighth note, whole note).
</pre>

---

## IV. Aggregation



## V. Strings

Strings can also be represented as arrays of characters ("char" data type). For example, all of the following
are valid:

```c++
// all of these are valid:
char myString[] = "arduino";
char myString[8] =  "arduino";
char myString[] = {'a', 'r', 'd', 'u', 'i', 'n', 'o'};
char myString[8] = {'a', 'r', 'd', 'u', 'i', 'n', 'o'};
char myString[8] = {'a', 'r', 'd', 'u', 'i', 'n', 'o', '\0'};

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
