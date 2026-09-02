**EXP NO: 18**

**GENERATION OF PWM USING TIMER INTERRUPT**

**AIM:**

To generate PWM using Timer interrupt.

**APPARATUS/SOFTWARE:**

PC Windows  
Keil µVision IDE  
8051 Simulator  
Serial Window UART #1

**PROGRAM:**

```c
#include <reg51.h>

sbit PWM = P1^0;
unsigned char count = 0;
unsigned char duty = 100;

void timer0_ISR(void) interrupt 1
{
  TH0 = 0xFC;
  TL0 = 0x66;

  count++;

  if(count < duty)
    PWM = 1;
  else
    PWM = 0;

  if(count >= 200)
    count = 0;
}

void main()
{
  TMOD = 0x01;
  TH0 = 0xFC;
  TL0 = 0x66;
  IE = 0x82;
  TR0 = 1;

  while(1);
}
```

**OUTPUT:**


<img width="934" height="580" alt="image" src="https://github.com/user-attachments/assets/88fe63ac-3cad-4429-b361-535115ac9530" />

<img width="925" height="570" alt="image" src="https://github.com/user-attachments/assets/f0eeefba-debb-4937-a683-89cae1ffd6c2" />

<img width="942" height="567" alt="image" src="https://github.com/user-attachments/assets/0e886eb8-4376-48b3-8598-07f462a8ca8b" />

**RESULT:**

```
PWM generated using Timer Interrupt for various duty cycles.
```
