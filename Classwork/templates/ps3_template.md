# Problem Set 3 Template

Copy the code below into a new Arduino sketch. Save your problem set in this format and email Ms. deBB this file to submit the assignment.

You can comment/ uncomment certain sections to test code by highlighting the area in question and pressing `CTRL + /` or `COMMAND + /`.

```c++

int test1[4] = {99, 68, 88, 92};
int test2[4] = {76, 92, 88, 81};

int studentGrades[11] = {94, 75, 69, 99, 88, 68, 90, 60, 80, 92, 67};

char sosPulse[21] = ". . .   - - -   . . .";

void setup(){
  Serial.begin(9600);

  //sumGrades();

  randomSeed(analogRead(0));
  //Serial.println("The winner is: " + getWinner());

}

void loop(){
  //sos();
}

// sumGrades()
// calculateAverage()


String getWinner() {
  String winner = "";
  int randNum = int(random(6));
  Serial.println(randNum);

  */ your code here */

  return winner;
}

```
