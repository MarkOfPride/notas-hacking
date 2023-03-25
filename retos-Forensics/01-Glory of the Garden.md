# Glory of the Garden

## Descripción
Este [jardín](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contiene más de lo que parece.

## Pistas
- ¿Qué es un editor hexadecimal?

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/GloryOfTheGarden]
└─$ strings garden.jpg -n 20 | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"
```

## Bandera
picoCTF{more_than_m33ts_the_3y3eBdBd2cc}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| strings -n | Imprime las cadenas de caracteres imprimibles en ficheros, el -n define un mínimo de caracteres |
| grep | Imprime líneas que coincidan con un patrón |

## Referencias
[strings(1) - Linux man page](https://linux.die.net/man/1/strings)
[grep(1) - Linux man page](https://linux.die.net/man/1/grep)
