# ASCII FTW

## Descripción
Este programa ha construido la bandera utilizando valores hexadecimales ascii. Identifique el texto de la bandera desensamblando el programa.
Puede descargar el archivo desde [aquí](https://artifacts.picoctf.net/c/508/asciiftw).

## Pistas
- El rango combinado de hex-ascii para alfabetos ingleses y dígitos numéricos es de 30 a 7A.
- Los conversores hexadecimal-ascii en línea pueden ser útiles.

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/ASCIIFTW]
└─$ gdb asciiftw -q            
GEF for linux ready, type `gef' to start, `gef config' to configure
88 commands loaded and 5 functions added for GDB 13.1 in 0.00ms using Python engine 3.11
Reading symbols from asciiftw...
(No debugging symbols found in asciiftw)
gef➤  disassemble main
Dump of assembler code for function main:
   0x0000000000001169 <+0>:     endbr64
   0x000000000000116d <+4>:     push   rbp
   0x000000000000116e <+5>:     mov    rbp,rsp
   0x0000000000001171 <+8>:     sub    rsp,0x30
   0x0000000000001175 <+12>:    mov    rax,QWORD PTR fs:0x28
   0x000000000000117e <+21>:    mov    QWORD PTR [rbp-0x8],rax
   0x0000000000001182 <+25>:    xor    eax,eax
   0x0000000000001184 <+27>:    mov    BYTE PTR [rbp-0x30],0x70
   0x0000000000001188 <+31>:    mov    BYTE PTR [rbp-0x2f],0x69
   0x000000000000118c <+35>:    mov    BYTE PTR [rbp-0x2e],0x63
   0x0000000000001190 <+39>:    mov    BYTE PTR [rbp-0x2d],0x6f
   0x0000000000001194 <+43>:    mov    BYTE PTR [rbp-0x2c],0x43
   0x0000000000001198 <+47>:    mov    BYTE PTR [rbp-0x2b],0x54
   0x000000000000119c <+51>:    mov    BYTE PTR [rbp-0x2a],0x46
   0x00000000000011a0 <+55>:    mov    BYTE PTR [rbp-0x29],0x7b
   0x00000000000011a4 <+59>:    mov    BYTE PTR [rbp-0x28],0x41
   0x00000000000011a8 <+63>:    mov    BYTE PTR [rbp-0x27],0x53
   0x00000000000011ac <+67>:    mov    BYTE PTR [rbp-0x26],0x43
   0x00000000000011b0 <+71>:    mov    BYTE PTR [rbp-0x25],0x49
   0x00000000000011b4 <+75>:    mov    BYTE PTR [rbp-0x24],0x49
   0x00000000000011b8 <+79>:    mov    BYTE PTR [rbp-0x23],0x5f
   0x00000000000011bc <+83>:    mov    BYTE PTR [rbp-0x22],0x49
   0x00000000000011c0 <+87>:    mov    BYTE PTR [rbp-0x21],0x53
   0x00000000000011c4 <+91>:    mov    BYTE PTR [rbp-0x20],0x5f
   0x00000000000011c8 <+95>:    mov    BYTE PTR [rbp-0x1f],0x45
   0x00000000000011cc <+99>:    mov    BYTE PTR [rbp-0x1e],0x41
   0x00000000000011d0 <+103>:   mov    BYTE PTR [rbp-0x1d],0x53
   0x00000000000011d4 <+107>:   mov    BYTE PTR [rbp-0x1c],0x59
   0x00000000000011d8 <+111>:   mov    BYTE PTR [rbp-0x1b],0x5f
   0x00000000000011dc <+115>:   mov    BYTE PTR [rbp-0x1a],0x38
   0x00000000000011e0 <+119>:   mov    BYTE PTR [rbp-0x19],0x39
   0x00000000000011e4 <+123>:   mov    BYTE PTR [rbp-0x18],0x36
   0x00000000000011e8 <+127>:   mov    BYTE PTR [rbp-0x17],0x30
   0x00000000000011ec <+131>:   mov    BYTE PTR [rbp-0x16],0x46
   0x00000000000011f0 <+135>:   mov    BYTE PTR [rbp-0x15],0x30
   0x00000000000011f4 <+139>:   mov    BYTE PTR [rbp-0x14],0x41
   0x00000000000011f8 <+143>:   mov    BYTE PTR [rbp-0x13],0x46
   0x00000000000011fc <+147>:   mov    BYTE PTR [rbp-0x12],0x7d
   0x0000000000001200 <+151>:   movzx  eax,BYTE PTR [rbp-0x30]
   0x0000000000001204 <+155>:   movsx  eax,al
   0x0000000000001207 <+158>:   mov    esi,eax
   0x0000000000001209 <+160>:   lea    rdi,[rip+0xdf4]        # 0x2004
   0x0000000000001210 <+167>:   mov    eax,0x0
   0x0000000000001215 <+172>:   call   0x1070 <printf@plt>
   0x000000000000121a <+177>:   nop
   0x000000000000121b <+178>:   mov    rax,QWORD PTR [rbp-0x8]
   0x000000000000121f <+182>:   xor    rax,QWORD PTR fs:0x28
   0x0000000000001228 <+191>:   je     0x122f <main+198>
   0x000000000000122a <+193>:   call   0x1060 <__stack_chk_fail@plt>
   0x000000000000122f <+198>:   leave
   0x0000000000001230 <+199>:   ret
End of assembler dump.
gef➤  quit
```

>[!solution]
>La bandera se encuentra pasando los siguientes caracteres de hexadecimal a ASCII:
>0x70
>0x69
>0x63
>0x6f
>0x43
>0x54
>0x46
>0x7b
>0x41
>0x53
>0x43
>0x49
>0x49
>0x5f
>0x49
>0x53
>0x5f
>0x45
>0x41
>0x53
>0x59
>0x5f
>0x38
>0x39
>0x36
>0x30
>0x46
>0x30
>0x41
>0x46
>0x7d

## Bandera
picoCTF{ASCII_IS_EASY_8960F0AF}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| gdb | El depurador de GNU, su propósito es permitirle ver lo que está pasando ''dentro'' de otro programa mientras se ejecuta-o lo que otro programa estaba haciendo en el momento en que se bloqueó. |

## Referencias
[gdb(1) - Linux man page](https://linux.die.net/man/1/gdb)