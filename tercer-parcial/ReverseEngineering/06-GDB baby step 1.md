# GDB baby step 1

## Descripción
¿Puedes averiguar qué hay en el registro `eax` al final de la función `main`? Pon tu respuesta en el formato picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su bandera sería `picoCTF{17}`.
Desmonta [esto](https://artifacts.picoctf.net/c/512/debugger0_a).

## Pistas
- gdb es un depurador muy bueno para este problema y muchos otros
- `main` es en realidad un símbolo reconocido que puede utilizarse con los comandos de gdb

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep1]
└─$ chmod +x debugger0_a 
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep1]
└─$ gdb debugger0_a -q
GEF for linux ready, type `gef' to start, `gef config' to configure
88 commands loaded and 5 functions added for GDB 13.1 in 0.00ms using Python engine 3.11
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
gef➤  disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   rbp
   0x000000000000112e <+5>:     mov    rbp,rsp
   0x0000000000001131 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000000000001134 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000001138 <+15>:    mov    eax,0x86342
   0x000000000000113d <+20>:    pop    rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
gef➤  quit
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep1]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x86342)
549698
>>> exit()
```

>[!solution]
>Primero se le dan permisos de ejecución al archivo dado, luego se usa `gdb` para desensamblar la función `main()`, ahí nos percatamos que lo unico que se hace es asignar el valor `0x86342` al registro `eax` que es 549698 en decimal y esa es nuestra bandera.

## Bandera
picoCTF{549698}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| gdb | El depurador de GNU, su propósito es permitirle ver lo que está pasando ''dentro'' de otro programa mientras se ejecuta-o lo que otro programa estaba haciendo en el momento en que se bloqueó. |

## Referencias
[gdb(1) - Linux man page](https://linux.die.net/man/1/gdb)
