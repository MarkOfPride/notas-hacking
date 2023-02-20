# Bandit Level 9 → Level 10

## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** en una de las pocas cadenas legibles por humanos, precedida de varios caracteres "=".

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solución
```bash
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
c========== the
h;========== password
========== isT
n.E========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| strings | Extrae fragmentos de texto |

## Referencias
[strings](https://respontodo.com/como-usar-el-comando-strings-en-linux/)