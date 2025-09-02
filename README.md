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
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      1200: 12           |        1204 : 24         |
|      1201: 34           |        1205 : 68         |
|      1202: 12           |        1206 : 00         |
|      1203: 34           |                          |

#### Manual Calculations

<img width="1114" height="940" alt="image" src="https://github.com/user-attachments/assets/4ab9dff6-2a97-4815-9a1d-cdf4bf050522" />

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="634" height="406" alt="Screenshot 2025-08-25 204719" src="https://github.com/user-attachments/assets/7a561a47-8a29-437e-b4de-797968ef7187" />

<img width="636" height="404" alt="Screenshot 2025-08-25 205813" src="https://github.com/user-attachments/assets/abb33c91-ea2a-43f4-8538-f6157f9966e9" />



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
```
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|         1200 : 12       |          1204: 00        |
|         1201 : 34       |          1205: 00        |
|         1202 : 12       |          1206: 00        |
|         1204 : 34       |                          |

#### Manual Calculations
<img width="1146" height="1280" alt="image" src="https://github.com/user-attachments/assets/f5d228cd-318a-44b6-a894-4573c05da296" />



## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="642" height="397" alt="Screenshot 2025-08-25 210519" src="https://github.com/user-attachments/assets/65f36d4f-5ec1-41db-9608-d96bd3b9ff88" />

<img width="637" height="403" alt="Screenshot 2025-08-25 210408" src="https://github.com/user-attachments/assets/0cdf9596-becd-49c7-a731-c70ff52a7409" />



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
ASSUME CS: CODE, DS: CODE
ORG 1000H
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
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      1200: 12           |         1204: 44         |
|      1201: 34           |         1205: 51         |
|      1202: 12           |         1206: 97         |
|      1203: 34           |         1207: 0A         |

#### Manual Calculations
<img width="1118" height="1118" alt="image" src="https://github.com/user-attachments/assets/d953def2-b4ec-4c9e-84e9-5d10b9de368a" />

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="637" height="393" alt="Screenshot 2025-08-25 213938" src="https://github.com/user-attachments/assets/8957c403-8aa3-4ae7-a114-72f2ab8c56e4" />

<img width="633" height="405" alt="Screenshot 2025-08-25 214651" src="https://github.com/user-attachments/assets/28598759-186a-4c42-93e0-b65cf1eb1fb0" />

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
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200: 12          |         1204: 01         |
|       1201: 34          |         1205: 00         |
|       1202: 12          |         1206: 00         |
|       1203: 34          |         1207: 00         |

#### Manual Calculations
<img width="1060" height="656" alt="image" src="https://github.com/user-attachments/assets/be357654-4734-4faf-81ca-4e75e1f621e2" />


## OUTPUT FROM MASM SOFTWARE
<img width="638" height="402" alt="Screenshot 2025-08-25 222516" src="https://github.com/user-attachments/assets/b4bacdb4-3ce9-4bb5-8b2c-dd74822ccc20" />

<img width="637" height="399" alt="Screenshot 2025-08-25 222622" src="https://github.com/user-attachments/assets/d6e46c60-63c8-48a0-96ba-9db8b04d0ea0" />

## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.
