.model small
display macro msg
lea dx,msg
mov ah,09h
int 21h
endm
.data
      msg1 db 0dh,0ah,"Enter a string$"
      msg2 db 0dh,0ah,"Entered string is palindrome$"
      msg3 db 0dh,0ah,"Entered string is not a palindrome$"
      str db 10h dup(0)
      revstr db 10h dup(0)
      len dw 0
.code
      mov ax,@data
      mov ds,ax
      display msg1
      mov SI,00h
Back1:mov ah,01h
      int 21h
      cmp al,0dh
      jz next
      mov str[SI],al
      inc SI
      inc len
      jmp Back1
next: mov SI,00h
      mov DI,00h
      add DI,len
      dec DI
      mov cx,len
back2: mov al,str[SI]
       mov revstr[DI],al
       inc SI
       dec DI
       loop back2
    mov cx,len
    mov SI,00h
    mov DI,00h
    CLD
back3: mov bl,str[SI]
       cmp bl,revstr[DI]
       jnz notall
       inc si
       inc di
       loop back3
       display msg2
       jmp last
notall: display msg3
last:mov ah,4ch
     int 21h
     end
