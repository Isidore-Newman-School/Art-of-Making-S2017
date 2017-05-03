# Problem Set 3. Arrays

Problem sets should be completed **individually**, but *if you have questions, don't hesitate to ask* for help. Problems sets are meant to cement your understanding of Arduino concepts.

**BEFORE BEGINNING ASSIGNMENT**

1. Copy the code [in this template](../templates/ps3_template.md) into a new Arduino project.
2. Put all problem set answers into this Arduino sketch
3. *To submit assignment*, email this fleshed-out template to Ms. deBB

---
**(0)** The grades for each student are stored in test1[] and test2[] arrays. Write a function **calculateAverage()** that takes a parameter- a student number (0, 1, 2, or 3)- and returns the student's average on both test1 and test2. It should print this average to the Serial Monitor.

```c++
int test1[4] = {99, 68, 88, 92};
int test2[4] = {76, 92, 88, 81};

void setup(){
  Serial.begin(9600);
}

void loop(){}

// calculateAverage()

```



**(1)** Create an array of 5 names. Finish filling out the **getWinner()** function so that it returns a randomly-selected name from the names array.

```c++
// your array

void setup(){
  Serial.begin(9600);
  randomSeed(analogRead(0));

  Serial.println("The winner is: " + getWinner());
}

void loop(){}

String getWinner() {
  String winner = "";
  int randNum = int(random(6));
  Serial.println(randNum);

  */ your code here */

  return winner;
}

```

**(2)** Write a function **sumGrades()** that counts how many As, Bs, or Cs in the **studentGrades[]** array. sumGrades() should print to the Serial Monitor:

  "As: 4"
  "Bs: 2"
  "Cs: 1"
  "Ds: 3"
  "Fs: 1"


```c++
int studentGrades[11] = {94, 75, 69, 99, 88, 68, 90, 60, 80, 92, 67};

void setup(){
  Serial.begin(9600);
  sumGrades();
}

void loop(){}

// sumGrades()

```

**(3)** The **sosPulses[]** array stores the morse code pulses of the SOS signal. Write a function **sos()** that uses a for loop and a conditional statement to make an LED blink the SOS signal in accordance with [International Morse Code Rules](http://morsecode.scphillips.com/morse2.html):

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
