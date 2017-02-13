# Problem Set 3. Arrays

Problem sets should be completed **individually**, but *if you have questions, don't hesitate to ask* for help. Problems sets are meant to cement your understanding of Arduino concepts.

**BEFORE BEGINNING ASSIGNMENT**

1. Copy the code [in this template](../templates/ps3_template.md) into a new Arduino project.
2. Put all problem set answers into this Arduino sketch
3. *To submit assignment*, email this fleshed-out template to Ms. deBB

---


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
