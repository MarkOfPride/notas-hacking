# Bandit Level 11 → Level 12

## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt**, donde todas las letras minúsculas (a-z) y mayúsculas (A-Z) se han girado 13 posiciones.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución
```bash
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ python3
Python 3.10.6 (main, Nov 14 2022, 16:10:14) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> codecs.decode('Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi','rot13')
'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'
>>> exit()
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| python3 | Abre el interprete de python3 en la consola |
| codecs.decode | Podemos decodificar la cadena binaria en forma normal |
| rot13 | Rota las posiciones de la cadena 13 veces (A-Z y a-z) |

## Referencias
[codecs.decode() in Python](https://www.geeksforgeeks.org/codecs-decode-in-python/)