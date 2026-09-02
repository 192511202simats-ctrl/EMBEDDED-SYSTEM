**EXP NO: 22**

**SERIAL TRANSMISSION AND RECEPTION USING ON-CHIP UART IN LPC2148 KIT**

**AIM:**

To write and execute C program for serial transmission and reception using on-chip UART in LPC2148 kit.

**APPARATUS:**

Keil uVision5  
Philips Flah Programmer  
LPC2148 kit

**PROGRAM:**

```c
#include <lpc214x.h>

void UART0_Init(void)
{
  PLL0CON = 0;
  PLL0FEED=0xAA;
  PLL0FEED=0x55;
  VPBDIV = 1;

  PINSEL0 |= 0x5;
  U0FCR = 0;
  U0LCR = 0x83;
  U0DLL = 0x27;
  U0DLM = 0;
  U0LCR = 3;
}

void sout(unsigned char dat1)
{
  while(!(U0LSR & 0x20));
  U0THR = dat1;
}

int main (void)
{
  int dat;

  UART0_Init();

  do
  {
    if(U0LSR & 1)
    {
      dat = U0RBR;
      sout(dat);
    }
  }while(1);
}
```

**OUTPUT:**


<img width="989" height="742" alt="image" src="https://github.com/user-attachments/assets/e8e97d8c-2041-47b0-9777-3eceb16d9c7b" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
