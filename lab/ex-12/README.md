**EXP NO: 12**

**EMBEDDED C PROGRAM TO MULTIPLY TWO 16-BIT BINARY NUMBERS**

**AIM:**

To write an Embedded C program to multiply two 16-bit numbers using Keil software.

**SOFTWARE REQUIRED:**

Keil

**PROGRAM:**

```c
#include <reg51.h>

void main()
{
  while (1)
  {
    unsigned int num1, num2;
    unsigned long int product;

    num1 = 0x2222;
    num2 = 0xBBBB;

    product = (unsigned long int)num1 * num2;

    P0 = product & 0xff;
    P1 = (product & 0xff00)>>8;
    P2 = (product & 0xff0000)>>16;
    P3 = (product & 0xff000000)>>24;
  }
}
```

**OUTPUT:**

<img width="941" height="500" alt="image" src="https://github.com/user-attachments/assets/c863ac1f-c08a-4413-9634-97e11c1885ad" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
