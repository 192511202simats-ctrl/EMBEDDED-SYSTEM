**EXP NO: 17**

**UART INTERFACING USING INTERRUPT IN KEIL**

**AIM:**

To receive serial data using interrupt.

**APPARATUS:**

PC Windows  
Keil µVision IDE  
8051 Simulator  
Serial Window UART #1

**PROGRAM:**

```c
#include <reg51.h>

void serial_ISR(void) interrupt 4
{
  if(RI)
  {
    P1 = SBUF;
    RI = 0;
  }
}

void main()
{
  TMOD=0x20;
  TH1=0xFD;
  SCON=0x50;
  TR1=1;
  ES=1;
  EA=1;

  while(1);
}
```

**OUTPUT:**


![Uploading image.png…]()


**RESULT:**

```
Thus the UART interfacing using interrupt program has been successfully verified and executed.
```
