**EXP NO: 2**

**GENERATION OF SQUARE WAVE USING PROTEUS**

**AIM:**

To write an assembly language program to Generate square wave using AT89C51.

**SOFTWARE REQUIRED:**

● Proteus 8 software.

**PROGRAM:**

```asm
ORG 0000H
UP: SETB P2.0
ACALL DELAY
CLR P2.0
ACALL DELAY
SJMP UP
DELAY: MOV R4,#35
H1:MOV R3,#255
H2:DJNZ R3,H2
DJNZ R4,H1
RET
END
```

**OUTPUT:**

<img width="941" height="497" alt="image" src="https://github.com/user-attachments/assets/fe226fa2-ef34-47e8-a1bf-f82c32e7f8ff" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
