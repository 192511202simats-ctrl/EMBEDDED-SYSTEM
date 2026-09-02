**EXP NO: 8**

**GAS SENSOR MQ-2 IN PROTEUS USING ARDUINO**

**AIM:**

To write an Embedded C program for interfacing Gas Sensor MQ-2 using Arduino Uno and Proteus

**SOFTWARE REQUIRED:**

● Proteus 8  
● Arduino IDE

**PROGRAM:**

```cpp
#define GreenLed 13
#define Sensor A0

void setup(){
  pinMode(13,OUTPUT);
  pinMode(12,OUTPUT);
  pinMode(A0,INPUT);
  Serial.begin(9600);
}

void loop() {
  int value = analogRead(A0);
  Serial.print("Analogic Value coming from the sensor : ");
  Serial.println(value);
  delay(100);

  if(value>600){
    digitalWrite(13,HIGH);
  }
  else{
    digitalWrite(13,LOW);
  }

  delay(20);
}
```

**Code for MQ6 sensor:**

```cpp
int mq6Pin = A0; // MQ-5 analog pin connected to A0

void setup() {
  Serial.begin(9600);
}

void loop() {
  int sensorValue =
  analogRead(mq5Pin);
  Serial.print("MQ5 Sensor Value: ");
  Serial.println(sensorValue);
  delay(1000); // 1-second delay
}
```

**OUTPUT:**

<img width="941" height="500" alt="image" src="https://github.com/user-attachments/assets/c11031a0-2f81-4a6d-8903-1e1ab9d769de" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
