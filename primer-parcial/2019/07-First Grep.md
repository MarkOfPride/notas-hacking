# First Grep

## Descripción
¿Puedes encontrar la bandera en el [archivo](https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file)? Esto sería realmente tedioso para mirar a través de forma manual, algo me dice que hay una mejor manera.

## Pistas
- grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución
```bash
markofpride-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file | grep pico
picoCTF{grep_is_good_to_find_things_f77e0797}
```

## Bandera
picoCTF{grep_is_good_to_find_things_f77e0797}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| curl | Es una herramienta para transferir datos desde o hacia un servidor |
| grep | Busca PATRONES en cada ARCHIVO |

## Referencias
[curl(1) — Linux manual page](https://man7.org/linux/man-pages/man1/curl.1.html)
[grep(1) — Linux manual page](https://man7.org/linux/man-pages/man1/grep.1.html)