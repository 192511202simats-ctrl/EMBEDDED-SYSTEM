**EXP NO: 21**

**DISPLAY A NUMBER IN SEVEN SEGMENT LED IN LPC2148 KIT**

**AIM:**

To write and execute C program to display a number in seven segment LED in LPC2148 kit

**APPARATUS:**

Keil uVision5 Software  
Philips Flah Programmer  
LPC 2148 kit

**PROGRAM:**

```c
#include <LPC214X.H>

#define DS3 1<<13
#define DS4 1<<12
#define SEG_CODE 0xFF<<16

unsigned char const seg_dat[]={
0x3F, 0x6, 0x5B, 0x4F, 0x66,
0x6D, 0x7D, 0x7, 0x7F, 0x67
};

void delayms(int n)
{
  int i,j;

  for(i=0;i<n;i++)
  {
    for(j=0;j<5035;j++);
  }
}

int main (void)
{
  unsigned char count;

  PINSEL0 = 0;
  PINSEL1 = 0;

  IODIR0 = SEG_CODE | DS3 | DS4;

  IOSET0 = SEG_CODE | DS3;
  IOCLR0 = DS4;

  count = 0;

  IOCLR0 = SEG_CODE;
  IOSET0 = seg_dat[count]<<16;

  while(1)
  {
    delayms(1000);
    count++;

    if(count>9)
      count=0;

    IOCLR0 = SEG_CODE;
    IOSET0 = seg_dat[count]<<16;
  }
}
```

**OUTPUT:**


<img width="945" height="630" alt="image" src="https://github.com/user-attachments/assets/c549069c-3845-4f6c-8b54-695b6e72c326" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
