# Wave a flag

## Descripción
¿Puede invocar banderas de ayuda para una herramienta o binario? [Este programa](https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm) tiene información extraordinariamente útil...

## Pistas
- Este programa sólo funcionará en el webshell o en otro ordenador Linux
- Para obtener el archivo accesible en su shell, introduzca lo siguiente en el Terminal prompt: `$ wget https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm`
- Ejecute este programa introduciendo lo siguiente en el Terminal: `$ ./warm`, pero primero tendrá que hacerlo ejecutable con `$ chmod +x warm`
- -h y --help son los argumentos más comunes que se dan a los programas para obtener más información de ellos
- No todos los programas implementan funciones de ayuda como -h y --help

## Solución
```bash
markofpride-picoctf@webshell:~$ curl -s https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm | strings | grep pico
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_616f7182}
```

## Bandera
picoCTF{b1scu1ts_4nd_gr4vy_616f7182}

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