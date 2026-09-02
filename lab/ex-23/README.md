**EXP NO: 23**

**ACCESS AN INTERNAL ADC AND DISPLAY THE BINARY OUTPUT IN LEDS IN LPC2148 KIT**

**AIM:**

To write and execute C program for accessing an internal ADC and display the binary output in LEDS in LPC2148 kit.

**APPARATUS:**

Keil uVision5  
Philips Flah Programmer  
LPC2148 kit

**PROGRAM:**

```c
#include <LPC214X.H>

#define LEDS 0xFF<<8

#define AD0_1 1<<24
#define CLK_DIV 1<<8
#define PDN 1<<21
#define SOC 1<<24
#define BURST 1<<16
#define DONE 1<<31

void delay(unsigned int k)
{
  unsigned int i,j;

  for (j=0; j<k; j++)
    for(i = 0; i<=800; i++);
}

void adc_init()
{
  unsigned long int ADC_CH;

  ADC_CH = 0 | 1 << 1;
  AD0CR = SOC | PDN | CLK_DIV | ADC_CH | BURST;
}

unsigned int adc_read(unsigned char channel)
{
  unsigned int aval;
  unsigned long int val;

  if (channel == 1) val = AD0DR1;
  else if (channel == 2) val = AD0DR2;
  else if (channel == 3) val = AD0DR3;

  val = val >> 6;
  val = val & 0x3FF;

  aval = val;
  return (aval);
}

int main(void)
{
  unsigned int tp1;

  IODIR0 = LEDS;
  PINSEL0 = 0;
  PINSEL1 = 0 | AD0_1;

  adc_init();

  do
  {
    tp1 = adc_read(1);
    tp1 = tp1 >> 2;

    IOSET0 = LEDS;
    IOCLR0 = tp1 << 8;

    delay(1000);
  }while(1);
}
```

**OUTPUT:**


<img width="922" height="558" alt="image" src="https://github.com/user-attachments/assets/937ff51a-3145-4fb1-aa93-b32d033b0c00" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
