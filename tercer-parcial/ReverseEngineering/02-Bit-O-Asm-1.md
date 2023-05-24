# Bit-O-Asm-1

## Descripción
¿Puedes averiguar qué hay en el registro `eax`? Pon tu respuesta en el formato picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su bandera sería `picoCTF{17}`.
Descargue el volcado de montaje [aquí](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

## Pistas
- Como ocurre con la mayoría de los ensambladores, hay mucho ruido en el volcado de instrucciones. Encuentra la línea que corresponde a esta pregunta y no te lo pienses dos veces.

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/Bit-O-Asm-1]
└─$ cat disassembler-dump0_a.txt  
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
```

>[!solution]
>La solución del reto se encuentra en la linea `<+15>:    mov    eax,0x30` que significa: toma el valor `0x30` y colocalo en `eax` y `0x30` en decimal es 48.

## Bandera
picoCTF{48}

## Notas adicionales
| Instrucción | Descripción |
|--------|--------|
| mov | La instrucción mov copia el elemento de datos al que hace referencia su segundo operando en la ubicación a la que hace referencia su primer operando. |

## Referencias
[x86 Assembly Guide](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html)