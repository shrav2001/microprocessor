.MODEL SMALL
DISPLAY Macro MSG
LEA DX,MSG
mov ah,09h
int 21h
endm
.DATA
    ARRAY DB 15H, 07H, 01H, 09H, 01H
    MSG3 DB 0DH,0AH, "enter the ele to be searched$"
    MSG1 DB 0DH,0AH, "FOUND...$";
    MSG2 DB 0DH, 0AH,"NOT FOUND...$"
.code

    MOV AX, @DATA
    MOV DS, AX 
    DISPLAY MSG3
    MOV AH,01H
    INT 21H
    sub al,30h
    ;mov key,Al
    MOV SI, 00h
    MOV CX, 05h
    
  NEXT: 
    ;MOV AL, ARRAY[SI]
    
    CMP AL,array[si]
    JE RESULT
    inc si
    LOOP NEXT 
    
    display msg2
    mov ax,4ch
    int 21h
  RESULT:

    DISPLAY MSG1
    int 21h
     MOV AX, 4CH
     INT 21H


END
