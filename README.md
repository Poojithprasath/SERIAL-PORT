
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
#include <reg51.h>
void main(void)
{
    unsigned char msg[] = "POOJITH PRASATH M";
    unsigned char i;
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;
    for(i = 0; msg[i] != '\0'; i++)
    {
        SBUF = msg[i];
        while(TI == 0);
        TI = 0;
    }

    while(1);
}


```

### OUTPUT:
### (i) Serial Port Transfer a Single Character
<img width="1262" height="555" alt="image" src="https://github.com/user-attachments/assets/453573b9-b984-428c-aaee-cb9fba3d0218" />


### (ii) Serial Port to Transfer a Message
<img width="1384" height="587" alt="image" src="https://github.com/user-attachments/assets/02190648-8487-42a5-b6b3-085ecadb53cb" />



### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
