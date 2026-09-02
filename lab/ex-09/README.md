**EXP NO: 9**

**ULTRASONIC SENSOR IN PROTEUS USING ARDUINO**

**AIM:**

To write an Embedded C program for interfacing Ultrasonic Sensor using Arduino Uno and Proteus

**SOFTWARE REQUIRED:**

● Proteus 8  
● Arduino IDE

**PROGRAM:**

```cpp
int trig = 10;
int echo = 9;
long duration;
int cm;

void setup() {
  pinMode(trig, OUTPUT);
  pinMode(echo,INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trig, LOW);
  delayMicroseconds(10);
  digitalWrite(trig, HIGH);
  delayMicroseconds(10);
  digitalWrite(trig, LOW);
  delayMicroseconds(10);
  duration = pulseIn(echo, HIGH);
  cm = (duration/2) * 0.034;

  Serial.print(" Distance = ");
  Serial.print(cm);
  Serial.println(" cm");
}
```

**OUTPUT:**

<img width="941" height="500" alt="image" src="https://github.com/user-attachments/assets/a454097a-a5fb-44fe-a37e-cd139bf4b77a" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
