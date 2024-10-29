# singleequal
org 100h
start:
mov ah,01h
int 21h
sub al,'0'
mov bl,al

mov ah,01h
int 21h
sub al,'0'
cmp bl,al
je equal
 
mov dx, offset notequal
mov ah,09h
int 21h
jmp done

equal:
mov dx,offset equalmsg
mov ah,09h
int 21h

done:
mov ah,4Ch
int 21h

equalmsg db 'Equal $',0
notequal db 'Not Equal $',0
