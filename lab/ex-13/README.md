**EXP NO: 13**

**EMBEDDED C PROGRAM TO ADD AN ARRAY OF 16-BIT NUMBERS AND STORE THE 32-BIT RESULT IN INTERNAL RAM**

**AIM:**

To write an Embedded C program to add an array of 16-bit numbers and store the results in internal RAM using Keil software.

**SOFTWARE REQUIRED:**

Keil

**PROGRAM:**

```c
#include <reg51.h>

void main(void)
{
  unsigned int i;
  unsigned int array[5] = {0x1111, 0x2222, 0x8888, 0x4444, 0xABCD};
  unsigned long sum = 0;

  for (i = 0; i < 5; i++)
  {
    sum = sum + array[i];
  }

  P0 = (unsigned char)(sum & 0xFF);
  P1 = (unsigned char)((sum >> 8) & 0xFF);
  P2 = (unsigned char)((sum >> 16) & 0xFF);

  while(1);
}
```

**OUTPUT:**

<img width="941" height="500" alt="image" src="https://github.com/user-attachments/assets/9d95d5ba-b2c9-49c6-8899-7cf8c2bed307" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
