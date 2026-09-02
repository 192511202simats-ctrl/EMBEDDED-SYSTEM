**EXP NO: 11**

**STUDY OF GPIO & BIT ADDRESSING IN AT89C51**

**AIM:**

To study GPIO control and bit-addressable SFR using Embedded C.

**SOFTWARE REQUIRED:**

Keil

**PROGRAM:**

```c
#include <reg51.h>

sbit LED1 = P1^0;
sbit LED2 = P1^1;

void delay()
{
  unsigned int i,j;
  for(i=0;i<200;i++)
    for(j=0;j<1000;j++);
}

void main()
{
  while(1)
  {
    LED1 = 1;
    LED2 = 0;
    delay();

    LED1 = 0;
    LED2 = 1;
    delay();
  }
}
```

**OUTPUT:**

<img width="941" height="502" alt="image" src="https://github.com/user-attachments/assets/176a6762-3bd4-4920-b2f0-51193de5d015" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
