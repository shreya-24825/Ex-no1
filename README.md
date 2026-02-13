# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV AX, CODE
    MOV DS, AX

    MOV SI,2000H
    MOV DX,0000H

    MOV AX,[SI]
    MOV BX,[SI+02H]

    ADD AX,BX

    MOV [SI+04H],AX
    MOV [SI+06H],DX

    MOV AH,4CH
    INT 21H

CODE ENDS
END START

```

#### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      2000 : 08          |        2004 : 0C         |
|      2001 : 00          |        2005 : 00         |  
|      2002 : 04          |        2006 : 00         |
|      2003 : 00          |        2007 : 00         |



#### Manual Calculations

![1](https://github.com/user-attachments/assets/e91ad90a-b365-4c5d-92bb-2166a60042d8)





## OUTPUT IMAGE FROM MASM SOFTWARE
![ADD](https://github.com/user-attachments/assets/99b798ad-e51d-4471-ac27-b6d784802bb0)



## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV AX, CODE
    MOV DS, AX

    MOV SI,2000H
    MOV DX,0000H

    MOV AX,[SI]
    MOV BX,[SI+02H]

    SUB AX,BX

    MOV [SI+04H],AX
    MOV [SI+06H],DX

    MOV AH,4CH
    INT 21H

CODE ENDS
END START
```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      2000 : 08          |        2004 : 04         |
|      2001 : 00          |        1205 : 00         |  
|      2002 : 04          |        2006 : 00         |
|      2003 : 00          |        2007 : 00         |

#### Manual Calculations

![2](https://github.com/user-attachments/assets/8b2026b8-f490-440c-b502-77034b6577b5)



## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="642" height="434" alt="SUB" src="https://github.com/user-attachments/assets/0baab1a2-3bdb-4743-85d9-96efa7e716a4" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV AX, CODE
    MOV DS, AX

    MOV SI,2000H
    MOV DX,0000H

    MOV AX,[SI]
    MOV BX,[SI+02H]

    MUL BX

    MOV [SI+04H],AX
    MOV [SI+06H],DX

    MOV AH,4CH
    INT 21H

CODE ENDS
END START
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      2000 : 04          |        2004 : 14         |
|      2001 : 00          |        1205 : 00         |  
|      2002 : 05          |        2006 : 00         |
|      2003 : 00          |        2007 : 00         |

#### Manual Calculations

![3](https://github.com/user-attachments/assets/adfafbe4-5788-4a2b-96ae-3f74294ecb61)


## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="635" height="433" alt="MUL" src="https://github.com/user-attachments/assets/a551171f-a7f8-4f68-8154-17c03273c094" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE

ORG 1000H

START:
    MOV AX, CODE
    MOV DS, AX

    MOV SI,2000H
    MOV DX,0000H        ; IMPORTANT: clear DX before DIV

    MOV AX,[SI]         ; Dividend (16-bit)
    MOV BX,[SI+02H]     ; Divisor (16-bit)

    DIV BX              ; DX:AX / BX
                        ; Quotient -> AX
                        ; Remainder -> DX

    MOV [SI+04H],AX     ; Store quotient
    MOV [SI+06H],DX     ; Store remainder

    INT 3               ; <-- stop here for DEBUG

CODE ENDS
END START
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      2000 : 0A          |        2004 : 02         |
|      2001 : 00          |        1205 : 00         |  
|      2002 : 05          |        2006 : 00         |
|      2003 : 00          |        2007 : 00         |


#### Manual Calculations

![4](https://github.com/user-attachments/assets/97719dc2-3e5a-4f91-bc76-b4e87b3142fa)


## OUTPUT FROM MASM SOFTWARE

<img width="644" height="433" alt="DIV1" src="https://github.com/user-attachments/assets/68a66b31-f762-4e76-bbd8-34e15bbdb0a3" />


## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

