# Static ain't always noise

## Descripción
¿Puedes mirar los datos en este binario: [static](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static)? Este [script BASH](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh) podría ayudarte.

## Pistas
- (None)

## Solución
```bash
markofpride-picoctf@webshell:~$ curl -s https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static | strings | grep pico
picoCTF{d15a5m_t34s3r_f5aeda17}
```

## Bandera
picoCTF{d15a5m_t34s3r_f5aeda17}

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