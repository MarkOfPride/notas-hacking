# 2Warm

## Descripción
¿Puedes convertir el número 42 (base 10) a binario (base 2)?

## Pistas
- Envíe su respuesta en el formato de bandera de nuestro concurso. Por ejemplo, si su respuesta es "11111", deberá enviar "picoCTF{11111}" como indicador.

## Solución
```bash
markofpride-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
```

## Bandera
picoCTF{101010}

## Notas adicionales
| Método en python | Descripción |
|--------|--------|
| bin() | Dado un número decimal, te devuelve su equivalente en binario |

## Referencias
[Cómo Convertir un Número Decimal en Binario en Python](https://www.codigopiton.com/como-convertir-decimal-en-binario-en-python/)