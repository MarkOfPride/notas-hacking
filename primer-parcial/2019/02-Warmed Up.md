# Warmed Up

## Descripción
¿Cuánto es 0x3D (base 16) en decimal (base 10)?

## Pistas
- Envíe su respuesta en nuestro formato de bandera. Por ejemplo, si su respuesta es "22", deberá enviar "picoCTF{22}" como indicador.

## Solución
```bash
markofpride-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x3D)
61
```

## Bandera
picoCTF{61}

## Notas adicionales
| Función en python | Descripción |
|--------|--------|
| int() | La función int() convierte el número hexadecimal predeterminado prefijado con 0x en un número entero de base 10 |

## Referencias
[Hexadecimal to decimal Python](https://www.etutorialspoint.com/index.php/585-hexadecimal-to-decimal-python)