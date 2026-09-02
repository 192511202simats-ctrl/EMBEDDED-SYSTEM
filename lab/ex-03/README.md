**EXP NO: 3**

**STEPPER MOTOR USING AT89C51 USING PROTEUS**

**AIM:**

To write an assembly language program for Stepper Motor Using AT89C51 using Keil and Proteus

**SOFTWARE REQUIRED:**

● Proteus 8 software.

**PROGRAM:**

```asm
ORG 0000H
UP: MOV P2,#09H
ACALL DELAY
MOV P2,#0CH
ACALL DELAY
MOV P2,#06H
ACALL DELAY
MOV P2,#03H
ACALL DELAY
SJMP UP
DELAY:MOV R4,#18
H1:MOV R3,#255
H2:DJNZ R3,H2
DJNZ R4,H1
RET
END
```

**OUTPUT:**

<img width="941" height="497" alt="image" src="https://github.com/user-attachments/assets/67bb650f-d50b-4b2f-8046-6b4b214aa337" />

**RESULT:**

```
Thus the program has been successfully verified and executed.
```
