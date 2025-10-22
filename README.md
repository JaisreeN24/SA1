
# EXCHANGE THE CONTENTS OF TWO MEMORY BLOCKS

## AIM
To exchange the contents of two memory blocks of equal length in assembly language program in 8086.

---
## APPARATUS REQUIRED
Personal Computer with MASM software

---
## Algorithm
1. Initialize the register AX with 5000H and load it into the DS and ES segments to set up memory for data operations.
2. Clear the direction flag using CLD to ensure string instructions increment memory addresses.
3. Set the source index SI to 1000H, the destination index DI to 3000H, and the counter CX to 10.
4. Execute REP MOVSB to copy 10 bytes from the source to the destination memory.
5. Set the source index SI to 2000H, the destination index DI to 1000H, and the counter CX to 10.
6. Execute REP MOVSB to copy the next 10 bytes from the source to the destination memory.
7. Set the source index SI to 3000H, the destination index DI to 2000H, and the counter CX to 10, then execute REP MOVSB to copy the final 10-byte block.
8. Execute INT 3H to terminate the program and signal the end of execution.
---
## PROGRAM

```
CODE SEGMENT
ASSUME CS: CODE
START: MOV AX, 5000H
MOV DS, AX
MOV ES, AX
CLD
MOV SI, 1000H
MOV DI, 3000H
MOV CX, 10
REP
MOVSB
MOV SI, 2000H
MOV DI, 1000H
MOV CX, 10
REP
MOVSB
MOV SI, 3000H
MOV DI, 2000H
MOV CX, 10
REP MOVSB
INT 3H
CODE ENDS
END START
```
---
## OUTPUT:

#### (a) Data in the memory before exchanging the data

<img width="804" height="542" alt="image" src="https://github.com/user-attachments/assets/f307ba2d-8809-42bb-a60a-0ed0bdd084ea" />

#### (b) Data in the memory after exchanging the data

<img width="809" height="538" alt="image" src="https://github.com/user-attachments/assets/03fb9f1a-4129-4083-a9e0-801a54eed066" />

---

## RESULT:
Thus, the contents of two memory blocks of equal length is exchanged successfully.
