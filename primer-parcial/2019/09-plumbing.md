# plumbing

## Descripción
A veces es necesario manejar los datos del proceso fuera de un archivo. ¿Puedes encontrar una manera de mantener la salida de este programa y buscar la bandera? Conéctate a jupiter.challenges.picoctf.org 14291.

## Pistas
- Recuerde que el formato de la bandera es picoCTF{XXXX}
- ¿Qué es una pipe? No, no ese tipo de pipe... Este [tipo](http://www.linfo.org/pipes.html)

## Solución
```bash
markofpride-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 | grep pico
picoCTF{digital_plumb3r_ea8bfec7}
^C
```

## Bandera
picoCTF{digital_plumb3r_ea8bfec7}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| nc | La utilidad nc (o netcat) se utiliza para casi cualquier cosa bajo el sol que implique TCP o UDP |
| grep | Busca PATRONES en cada ARCHIVO |

## Referencias
[nc(1) - Linux man page](https://linux.die.net/man/1/nc)
[grep(1) — Linux manual page](https://man7.org/linux/man-pages/man1/grep.1.html)

