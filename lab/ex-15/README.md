**EXP NO: 15**

**EMBEDDED C PROGRAM TO CONVERT THE HEXADECIMAL DATA 0XCFH TO DECIMAL AND DISPLAY THE DIGITS ON PORTS P0, P1 AND P2**

**AIM:**

To write an Embedded C program to convert Hexadecimal numbers into Decimal and display the digits on ports using Keil software.

**SOFTWARE REQUIRED:**

Keil software

**PROGRAM:**

```c
#include <reg51.h>

void main(void)
{
  unsigned char hexa = 0x08;
  unsigned char hundreds, tens, units;

  ACC = hexa;
  B = 10;
  ACC = ACC / B;
  units = B;

  B = 10;
  ACC = ACC / B;
  tens = B;

  hundreds = ACC;

  P0 = units;
  P1 = tens;
  P2 = hundreds;

  while(1);
}
```

**OUTPUT:**

<img width="941" height="730" alt="image" src="https://github.com/user-attachments/assets/4f863044-fdf1-4b38-9f8c-6fa296f03ee7" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
