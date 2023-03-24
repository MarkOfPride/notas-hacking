# Bases

## Descripción
¿Qué significa **bDNhcm5fdGgzX3IwcDM1**? Creo que tiene algo que ver con las bases.

## Pistas
- Envíe su respuesta en nuestro formato de bandera. Por ejemplo, si su respuesta es "hola", deberá enviar "picoCTF{hello}" como bandera.

## Solución
```bash
markofpride-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode("bDNhcm5fdGgzX3IwcDM1")
b'l3arn_th3_r0p35'
```

## Bandera
picoCTF{l3arn_th3_r0p35}

## Notas adicionales
| Método en python | Descripción |
|--------|--------|
| base64.b64decode() | Decodifica el objeto similar a bytes codificado en Base64 o cadena de caracteres ASCII s y retorna los bytes decodificados |

## Referencias
[base64](https://docs.python.org/es/3/library/base64.html#module-base64)