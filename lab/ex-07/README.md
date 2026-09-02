**EXP NO: 7**

**SERIAL COMMUNICATION USING ARDUINO WITH PROTEUS**

**AIM:**

To write an Embedded C program for serial communication using Arduino Uno and Proteus

**SOFTWARE REQUIRED:**

● Proteus 8  
● Arduino IDE

**PROGRAM:**

```cpp
void setup()
{
  Serial.begin(9600); // send and receive at 9600 baud
}

int number = 0;

void loop()
{
  Serial.print("Number is ");
  Serial.println(number); // print the number
  delay(500); // delay half second between numbers
  number++; // to the next number
}
```

**OUTPUT:**

<img width="794" height="519" alt="image" src="https://github.com/user-attachments/assets/3a72a963-80a2-4a36-9864-984ff9f80b4b" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
