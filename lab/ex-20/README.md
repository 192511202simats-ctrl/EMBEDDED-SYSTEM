**EXP NO: 20**

**PROGRAM TO READ THE SWITCH AND DISPLAY IN THE LEDS USING LPC2148 KIT**

**AIM:**

To write and execute C program to read the switch and display in the LEDs using LPC2148 kit

**APPARATUS:**

Keil uVision5 Software  
Philips Flah Programmer  
LPC 2148 kit

**PROGRAM:**

```c
#include "lpc214x.h"

int main(void)
{
  unsigned int sw_sts;

  IODIR0 = 0x0000ff00;
  PINSEL0 = 0;

  while(1)
  {
    sw_sts = IOPIN0;

    IOSET0 = 0x0000ff00;
    IOCLR0 = sw_sts >> 8;
  }
}
```

**OUTPUT:**


<img width="994" height="530" alt="image" src="https://github.com/user-attachments/assets/37ba7424-9d02-41e6-8c44-fcb3ea081539" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
