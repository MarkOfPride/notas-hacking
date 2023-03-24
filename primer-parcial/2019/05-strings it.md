# strings it

## Descripción
¿Puedes encontrar la bandera en el [archivo](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) sin ejecutarlo?

## Pistas
- [strings](https://linux.die.net/man/1/strings)

## Solución
```bash
markofpride-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings | strings | grep pico
picoCTF{5tRIng5_1T_d66c7bb7}
```

## Bandera
picoCTF{5tRIng5_1T_d66c7bb7}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| curl | Es una herramienta para transferir datos desde o hacia un servidor |
| strings | Imprimir las secuencias de caracteres imprimibles en ficheros |
| grep | Busca PATRONES en cada ARCHIVO |

## Referencias
[curl(1) — Linux manual page](https://man7.org/linux/man-pages/man1/curl.1.html)
[strings(1) — Linux manual page](https://man7.org/linux/man-pages/man1/strings.1.html)
[grep(1) — Linux manual page](https://man7.org/linux/man-pages/man1/grep.1.html)