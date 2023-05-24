# Bit-O-Asm-2

## Descripción
¿Puedes averiguar qué hay en el registro `eax`? Pon tu respuesta en el formato picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su bandera sería `picoCTF{17}`.
Descargue el volcado de montaje [aquí](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

## Pistas
- Los `PTR` o "punteros", hacen referencia a una ubicación en memoria donde se pueden almacenar valores

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/Bit-O-Asm-2]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/reversing/Bit-O-Asm-2]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x9fe1a)
654874
>>> exit()
```

>[!solution]
>La solución del reto se encuentra en las linea `<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a` y `<+22>:    mov    eax,DWORD PTR [rbp-0x4]` en la primera se pone el valor `0x9fe1a` en la posicion de memoria `-0x4` y en la segunda se asigna ese dato al registro `eax`, para encontrar la bandera se tiene que transformar ese valor a decimal lo que da `654874` como resultado.

## Bandera
picoCTF{654874}

## Notas adicionales
| Instrucción | Descripción |
|--------|--------|
| mov | La instrucción mov copia el elemento de datos al que hace referencia su segundo operando en la ubicación a la que hace referencia su primer operando. |

## Referencias
[x86 Assembly Guide](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html)