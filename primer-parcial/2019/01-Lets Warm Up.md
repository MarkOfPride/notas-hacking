# Lets Warm Up 

## Descripción
Si te dijera que una palabra empieza por 0x70 en hexadecimal, ¿con qué empezaría en ASCII?

## Pistas
- Envíe su respuesta en nuestro formato de bandera. Por ejemplo, si su respuesta es "hola", deberá enviar "picoCTF{hello}" como bandera.

## Solución
```bash
markofpride-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x70)
'p'
```

## Bandera
picoCTF{p}

## Notas adicionales
| Método en python | Descripción |
|--------|--------|
| chr() | Esto recibe un número y devuelve su representación como carácter |

## Referencias
[Funciones ord y chr en Python](https://parzibyte.me/blog/2018/12/10/ord-chr-python/)

