# Guide for Python-Assembler

### Register

In this programming language you can use four registers. 
* eax
* ebx
* ecx
* edx

The register **eax** will be standard use for multiplication and division. 
Commands for arithmetic are:

* add  p0, p1
* sub  p0, p1
* mul  [register]
* div   [register]

p0 and p1 stands for parameter. p0 must be a register, p1 can be a register or constant.
The commands **mul** and **div** standard use eax. For instance:

```
mov ecx, 56
sub ecx, 10
mov eax, 4
int 0x80 

```

* The first line move the number  56 into register ecx.
* The second line subtract 10 from the ecx register.
* The third line move the number 4 into the eax register. This is for the print-function. 
* The fourt line call interrupt 0x80, thus the result will print onto console.
* The fifth line is a new line. This is important.

**Important: close each line with a newline!**

### System-Functions

With the interrupt 0x80 you can use some functionality in your program. 

EAX  | Function 
---- | ---------
1   | exit program. error code in ebx
3   | read input. onto ecx (only float)
4   | output onto console. print content in ecx

EAX stands for the register eax

### Variables

Variables begin with a $ or written in uppercase.

For instance:

```

; variables
VAR1 db 56
$var1 db 10

mov ecx, VAR1
mov ebx, $var1
sub ecx, ebx
mov eax, 4
int 0x80

```

**Important: The arithmetic commands (add, sub) works only with registers or constans. 
Therefore we must use the register ebx as a placeholder, above.**

Result of code, above.

```
46
```
### Comments

Comments begin with ; and ends with a newline. 
We noticed a comment, above. 


