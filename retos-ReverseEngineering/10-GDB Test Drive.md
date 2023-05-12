# GDB Test Drive

## Descripción
¿Puedes conseguir la bandera?
Descarga este [binario](https://artifacts.picoctf.net/c/85/gdbme).
Aquí están las instrucciones de prueba:
-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`

## Pistas
- (None)

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/GDBTestDrive]
└─$ chmod +x gdbme
                                                          
┌──(kali㉿kali)-[~/picoctf/reversing/GDBTestDrive]
└─$ gdb gdbme -q  
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) break *(main+99)
Breakpoint 1 at 0x132a
(gdb) run
Starting program: /home/kali/picoctf/reversing/GDBTestDrive/gdbme 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055555555532a in main ()
(gdb) jump *(main+104)
Continuing at 0x55555555532f.
picoCTF{d3bugg3r_dr1v3_197c378a}
[Inferior 1 (process 5039) exited normally]
(gdb) exit
```

## Bandera
picoCTF{d3bugg3r_dr1v3_197c378a}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| gdb | El propósito de un depurador como GDB es permitirle ver lo que está pasando ''dentro'' de otro programa mientras se ejecuta o lo que otro programa estaba haciendo en el momento en que se bloqueó |

## Referencias
[gdb(1) - Linux man page](https://linux.die.net/man/1/gdb)