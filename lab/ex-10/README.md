**EXP NO: 10**

**PIR SENSOR IN PROTEUS USING ARDUINO**

**AIM:**

To write an Embedded C program for interfacing PIR Sensor using Arduino Uno and Proteus

**SOFTWARE REQUIRED:**

● Proteus 8  
● Arduino IDE

**PROGRAM:**

```cpp
int Status = 13; // Digital pin D6
int sensor = 12; // Digital pin D7

void setup() {
  Serial.begin(9600);
  pinMode(sensor, INPUT); // declare sensor as input
  pinMode(Status, OUTPUT); // declare LED as output
}

void loop() {
  long state = digitalRead(sensor);
  Serial.println(state);

  if(state == HIGH) {
    digitalWrite (Status, HIGH);
    Serial.println("Motion detected!");
    delay(1000);
  }
  else {
    digitalWrite (Status, LOW);
    Serial.println("Motion absent!");
    delay(1000);
  }
}
```

**OUTPUT:**

<img width="941" height="498" alt="image" src="https://github.com/user-attachments/assets/d7501d49-2edb-4c35-b603-51801c34cbc1" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
