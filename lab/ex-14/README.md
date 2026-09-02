**EXP NO: 14**

**EMBEDDED C PROGRAM TO DISPLAY "HELLO WORLD" MESSAGE**

**AIM:**

To write an Embedded C program to display “HELLO WORLD” message using Keil software.

**SOFTWARE REQUIRED:**

Keil software

**PROGRAM:**

```c
#include <reg51.h>
#include <stdio.h>

void main (void){
  SCON = 0x50;
  TMOD = 0x20;
  TH1 = 0xFD;
  TR1 = 1;
  TI = 1;

  while (1)
  {
    printf ("Hello World ! \n ");
  }
}
```

**OUTPUT:**

![Uploading image.png…]()


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
