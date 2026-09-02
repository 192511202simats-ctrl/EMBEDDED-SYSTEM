**EXP NO: 16**

**SERIAL INTERRUPT USING UART (KEYBOARD INPUT) IN KEIL**

**AIM:**

To write and simulate an Embedded C program using serial interrupt in 8051 microcontroller such that while a message is continuously transmitted, any key pressed from the keyboard generates an interrupt and is displayed through UART.

**APPARATUS/SOFTWARE:**

PC Windows  
Keil µVision IDE  
8051 Simulator  
Serial Window (UART #1)

**PROGRAM:**

```c
#include <reg51.h>
#include <stdio.h>

void serial_ISR(void) interrupt 4
{
  char ch;

  if (RI)
  {
    RI = 0;
    ch = SBUF;

    printf("\n>>> INTERRUPT RECEIVED: ");
    printf("%c\n", ch);
  }
}

void delay(void)
{
  unsigned int i;

  for(i = 0; i < 50000; i++);
}

void main(void)
{
  SCON = 0x50;
  TMOD = 0x20;
  TH1 = 0xFD;
  TR1 = 1;

  IE = 0x90;
  TI = 1;

  while(1)
  {
    printf("Hello World\n");
    delay();
  }
}
```

**OUTPUT:**


<img width="864" height="539" alt="image" src="https://github.com/user-attachments/assets/6023fe5e-4d8c-440f-b0fa-6575607ed532" />


**RESULT:**

```
Serial interrupt using UART successfully implemented and verified in Keil simulator; keyboard input triggered interrupt and ISR serviced it.
```
