**EXP NO: 6**

**ARDUINO TO 16x2 LCD DISPLAY USING PROTEUS**

**AIM:**

To write an Embedded C program to interface Arduino Uno and 16 x 2 LCD display using Arduino Uno and Proteus

**SOFTWARE REQUIRED:**

● Proteus 8 software.  
● Arduino IDE software

**PROGRAM:**

```cpp
#include <LiquidCrystal.h>
LiquidCrystal lcd (7, 8, 9, 10, 11, 12);
// your PWM numbers may be different
void setup() {
  lcd.begin(16, 2);
  lcd.print("put your message here");
}
void loop () {
  for (int i=0; 1<13; i++)
}
lcd.scrollDisplayLeft();
delay(700);
}
}
```

**OUTPUT:**

<img width="815" height="510" alt="image" src="https://github.com/user-attachments/assets/d2ae0be7-04df-4b81-99d2-c68f94154e0c" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
