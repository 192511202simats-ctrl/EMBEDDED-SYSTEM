**EXP NO: 1**

**FLASHING OF LED USING AT89C51 MICROCONTROLLER USING PROTEUS**

**AIM:**

To Write an assembly language program to flash the LED using AT89C51

**SOFTWARES REQUIRED:**

● Proteus software

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
<img width="906" height="484" alt="image" src="https://github.com/user-attachments/assets/6d302bf3-94d0-40fa-981f-3b2c872cf39f" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```


