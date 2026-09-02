**EXP NO: 4**

**7 SEGMENT DISPLAY USING AT89C51 USING PROTEUS**

**AIM:**

To write an assembly language program for 7 Segment Display Using AT89C51 using Keil and Proteus

**SOFTWARE REQUIRED:**

● Proteus 8 software.

**PROGRAM:**

```asm
ORG 000H
UP:MOV P2,#0C0H
ACALL DELAY
MOV P2,#0F9H
ACALL DELAY
MOV P2,#0A4H
ACALL DELAY
MOV P2,#0B0H
ACALL DELAY
MOV P2,#99H
ACALL DELAY
MOV P2,#92H
ACALL DELAY
MOV P2,#82H
ACALL DELAY
MOV P2,#0F8H
ACALL DELAY
MOV P2,#80H
ACALL DELAY
MOV P2,#90H
ACALL DELAY

DELAY: MOV R5,#10
H1:MOV R4,#180
H2:MOV R3,#255
H3:DJNZ R3,H3
DJNZ R4,H2
DJNZ R5,H1
RET
END
```

**OUTPUT:**

<img width="860" height="511" alt="image" src="https://github.com/user-attachments/assets/ce1727be-4f07-41b6-81a8-80e2584cd6fb" />



**RESULT:**

```
Thus the program has been successfully verified and executed.
```


