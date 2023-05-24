# Bit-O-Asm-3

## Descripción
¿Puedes averiguar qué hay en el registro `eax`? Pon tu respuesta en el formato picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su bandera sería `picoCTF{17}`.
Descargue el volcado de montaje [aquí](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Pistas
- No todo en este listado de desmontaje es óptimo.

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/Bit-O-Asm-3]
└─$ cat disassembler-dump0_c.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/Bit-O-Asm-3]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x9fe1a * 0x4
2619496
>>> 2619496 + 0x1f5
2619997
>>> exit()
```

>[!solution]
>Primero notamos que al registro `eax` se le coloca `0x9fe1a`, luego se le multiplica por `0x4` para posteriormente sumarle `0x1f5` y así encontrar la bandera: 2619997.

## Bandera
picoCTF{2619997}

## Notas adicionales
| Instrucción | Descripción |
|--------|--------|
| mov | La instrucción mov copia el elemento de datos al que hace referencia su segundo operando en la ubicación a la que hace referencia su primer operando. |
| imul | La forma de dos operandos multiplica sus dos operandos juntos y almacena el resultado en el primer operando. El operando resultante debe ser un registro. |
| add | La instrucción add suma sus dos operandos, almacenando el resultado en su primer operando. Tenga en cuenta que, aunque ambos operandos pueden ser registros, como máximo un operando puede ser una posición de memoria. |

## Referencias
[x86 Assembly Guide](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html)