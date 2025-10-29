
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FDH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B' 
 WAIT:JNB TI, WAIT
 CLR TI 
 END

```
### (ii) Serial Port to Transfer a Message

```
ORG 00H 
MOV DPTR, #4500H
MOV TMOD, #20H 
MOV TH1, #0FDH 
MOV SCON, #40H 
SETB TR1 
AGAIN: MOVX A,@DPTR
MOV SBUF, A
 WAIT:JNB TI, WAIT
 CLR TI 
 INC DPTR
 SJMP AGAIN
 END

```

### OUTPUT:
### (i) Serial Port Transfer a Single Character
<img width="871" height="401" alt="image" src="https://github.com/user-attachments/assets/06a263fe-eae8-46da-a533-89d06d2a2782" />

### (ii) Serial Port to Transfer a Message
<img width="1306" height="534" alt="image" src="https://github.com/user-attachments/assets/bd30f406-ca39-47ea-8c43-ac81b944e38a" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
