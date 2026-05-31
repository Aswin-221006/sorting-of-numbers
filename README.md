# sorting-of-numbers
## Aim
To write and execute an Assembly Language Program for sorting data in Ascending and  descending order using 8051 microcontroller on Keil software.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)
1. Initialize the register **R7** with count (number of elements).  
2. Get the first two elements into two registers.  
3. Compare the two elements:  
   - If the value in register **R0** is lower, exchange **A** and **R0** data.  
   - Otherwise, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0** → if yes, move the register **R0 & A**.  
5. Increment pointer and decrement **R7**.  
6. If **R7 ≠ 0**, repeat from Step 2.  
7. Otherwise, stop the program.  
---

## Program (Ascending order)

```asm
ORG 0000H
       MOV R7,30H     
       DEC R7         

LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT

NEXT:  JC DOWN

       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R7,LOOP1

HERE:  SJMP HERE

END



```
## OUTPUT(Ascending order)
<img width="610" height="181" alt="552980210-b887ed8a-3bfe-4a96-9d80-1acda323367b" src="https://github.com/user-attachments/assets/7d161046-67e6-40d1-9ac0-723e1609dee2" />
<img width="602" height="188" alt="552980289-3f0b0b84-187d-468f-b90b-1a3f22239ee9" src="https://github.com/user-attachments/assets/0a20e034-cc98-4f83-8942-8d279db0feeb" />
Sorted array in ascending order
<img width="831" height="563" alt="552980443-b67edb49-c067-4d3b-9732-8c469f3e45fc" src="https://github.com/user-attachments/assets/a08db643-9b4e-4639-bc5e-47bec90ca74c" />
Memory window
<img width="673" height="205" alt="552980453-462f03cb-97a8-44dd-b63a-5592be068679" src="https://github.com/user-attachments/assets/065c9d3d-5455-4cc0-ba78-4fddfafd30ec" />




---

## Algorithm(Descending order)
1. Initialize the register **R7** with count.  
2. Get first two elements in two registers.  
3. Compare the two elements of data:  
   - If the value of **R0** register is high, then exchange **A** and **R0** data.  
   - Else, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0**, then move the contents of **R0** and **A**.  
5. Again increment pointer and decrement **R7**.  
6. Check if **R7 = 0**:  
   - If **No**, repeat the process from Step 2.  
   - If **Yes**, stop the program.  
---
## Program (Descending order)

```asm
ORG 0000H
       MOV R7,30H     ; Load number of elements
       DEC R7         ; Outer loop = n-1
	   
LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT

NEXT:  JNC DOWN       ; If A > B ? correct order ? skip
       ; Swap when A < B
       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R7,LOOP1

HERE:  SJMP HERE

END



```
## OUTPUT(Descending order)
<img width="564" height="159" alt="552991608-ca376b06-5283-4c76-897a-0607c9edee3f" src="https://github.com/user-attachments/assets/b024b6d6-b5f0-42b7-873b-300c0d5a243b" />
<img width="564" height="158" alt="552991632-3996e407-ccbd-4920-a01e-d9d99b573542" src="https://github.com/user-attachments/assets/9925c265-33f1-43bf-882b-c91e8c308508" />
Sorted array in descending order
<img width="940" height="558" alt="552991653-84830f13-9c77-4afc-8a99-486e32f0efc2" src="https://github.com/user-attachments/assets/cc473deb-a8b6-440c-93a0-8a39274b02ee" />
Memory Window
<img width="676" height="161" alt="552991658-35e348cd-b5d7-41ab-b084-2f08e334df08" src="https://github.com/user-attachments/assets/c749ff47-2efc-4e33-a106-ac84a79b98ac" />



---
## RESULT:
Thus the sorting of given data was done using 8051 keil software.

