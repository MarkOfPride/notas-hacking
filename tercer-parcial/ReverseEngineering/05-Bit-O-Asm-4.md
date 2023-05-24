# Bit-O-Asm-4

## Descripción
¿Puedes averiguar qué hay en el registro `eax`? Pon tu respuesta en el formato picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su bandera sería `picoCTF{17}`.
Descargue el volcado de montaje [aquí](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Pistas
- No le digas a nadie que te he dicho esto, pero puedes resolver este problema sin entender la relación comparar/saltar
- Por supuesto, si eres realmente bueno, sólo necesitarás un intento para resolver este problema

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/Bit-O-Asm-4]
└─$ cat disassembler-dump0_d.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/Bit-O-Asm-4]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x9fe1a < 0x2710
False
>>> 0x9fe1a - 0x65
654773
>>> exit()
```

>[!solution]
>Primero se compara el valor `0x9fe1a` para ver si es menor que `0x65` como es falso, se le resta a `0x9fe1a` el valor `0x65` lo que resulta en 654773 y salta a la linea `<main+41>` lo que asigna el valor  654773 a `eax` y esa es la bandera.

## Bandera
picoCTF{654773}

## Notas adicionales
| Instrucción | Descripción |
|--------|--------|
| mov | La instrucción mov copia el elemento de datos al que hace referencia su segundo operando en la ubicación a la que hace referencia su primer operando. |
| cmp | Compara los valores de los dos operandos especificados, estableciendo los códigos de condición en la palabra de estado de la máquina según corresponda. Esta instrucción es equivalente a la instrucción sub, salvo que el resultado de la resta se descarta en lugar de sustituir al primer operando. |
| add | La instrucción add suma sus dos operandos, almacenando el resultado en su primer operando. Tenga en cuenta que, aunque ambos operandos pueden ser registros, como máximo un operando puede ser una posición de memoria. |
| jmp | Transfiere el flujo de control del programa a la instrucción en la posición de memoria indicada por el operando. |

## Referencias
[x86 Assembly Guide](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html)