**EXP NO: 19**

**BLINKING LEDS USING SOFTWARE DELAY ROUTINE IN LPC2148 KIT**

**AIM:**

To write and execute a C program to blink LEDs using software delay routine in LPC 2148 kit

**APPARATUS:**

Keil uVision5 Software  
Philips Flah Programmer  
LPC 2148 kit

**PROGRAM:**

```c
#include "lpc214x.h"

void delay (unsigned int k);

void main(void)
{
  IODIR0 = 0xFFFFFFFF;
  PINSEL0 = 0;

  while(1)
  {
    IOSET0 = 0x0000ff00;
    delay(1000);

    IOCLR0 = 0x0000ff00;
    delay(1000);
  }
}

void delay(unsigned int k)
{
  unsigned int i,j;

  for (j=0; j<k; j++)
    for(i = 0; i<=800; i++);
}
```

**OUTPUT:**

LEDs P0.15-P0.8 are blinking

**RESULT:**

```
Thus the program has been successfully verified and executed.
```
