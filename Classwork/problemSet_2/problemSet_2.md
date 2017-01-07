loops

**(1)** In computer science the "%" (a.k.a. the modulo operator) is surprisingly useful. It is used to calculate the remainder after dividing two numbers. E.g.:

    5%2 = 1;
    4%2 = 0;
    3%2 = 1;
    2%2 = 0;
    1%2 = 1;
    0%2 = 0;

Use the modulo operator to write a function **fizzBuzz()** that uses Serial.println() to print the numbers from 1 to 100, with two exceptions:

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
