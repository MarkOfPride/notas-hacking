# Need For Speed

## Descripción
El nombre del juego es [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). ¿Eres lo suficientemente rápido para resolver este problema y mantenerlo por encima de 80 km/h?  [need-for-speed](https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed).

## Pistas
- ¿Cuál es la clave final?

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/NeedForSpeed]
└─$ gdb need-for-speed -q
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) break main
Breakpoint 1 at 0x91e
(gdb) info breakpoints
Num     Type           Disp Enb Address            What
1       breakpoint     keep y   0x000000000000091e <main+4>
(gdb) run
Starting program: /home/kali/picoctf/reversing/NeedForSpeed/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055555540091e in main ()
(gdb) disassemble main
Dump of assembler code for function main:
   0x000055555540091a <+0>:     push   %rbp
   0x000055555540091b <+1>:     mov    %rsp,%rbp
=> 0x000055555540091e <+4>:     sub    $0x10,%rsp
   0x0000555555400922 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000555555400925 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000555555400929 <+15>:    mov    $0x0,%eax
   0x000055555540092e <+20>:    call   0x5555554008d8 <header>
   0x0000555555400933 <+25>:    mov    $0x0,%eax
   0x0000555555400938 <+30>:    call   0x55555540082f <set_timer>
   0x000055555540093d <+35>:    mov    $0x0,%eax
   0x0000555555400942 <+40>:    call   0x55555540087d <get_key>
   0x0000555555400947 <+45>:    mov    $0x0,%eax
   0x000055555540094c <+50>:    call   0x5555554008ac <print_flag>
   0x0000555555400951 <+55>:    mov    $0x0,%eax
   0x0000555555400956 <+60>:    leave
   0x0000555555400957 <+61>:    ret
End of assembler dump.
(gdb) call (int) header()
Keep this thing over 50 mph!
============================

$1 = 2
(gdb) call (int) get_key()
Creating key...
Finished
$2 = 9
(gdb) call (int) print_flag()
Printing flag:
PICOCTF{Good job keeping bus #1f2ac4ec speeding along!}
$3 = 56
(gdb) exit
```

## Bandera
PICOCTF{Good job keeping bus \#1f2ac4ec speeding along!}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| gdb | El propósito de un depurador como GDB es permitirle ver lo que está pasando ''dentro'' de otro programa mientras se ejecuta o lo que otro programa estaba haciendo en el momento en que se bloqueó |
| (gdb) break | Crea un punto donde la ejecución del programa se detiene |
| (gdb) run | Inicia el flujo de ejecución del programa |
| (gdb) call | Llama a un método especifico dentro del flujo del programa |

## Referencias
[gdb(1) - Linux man page](https://linux.die.net/man/1/gdb)
[GDB Documentation](https://www.sourceware.org/gdb/documentation/)