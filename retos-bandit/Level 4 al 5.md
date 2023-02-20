# Bandit Level 4 → Level 5

## Objetivo
La contraseña para el siguiente nivel se almacena en el único archivo legible por humanos en el directorio **inhere**. Consejo: si su terminal está estropeada, pruebe el comando "reset".

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit4
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Solución
```bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ cat ./-file00
T߼��B�������#6�Kt�3�
                     �6X��t���)bandit4@bandit:~/inhere$ file ./-file00
./-file00: data
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| file | Determina el tipo de archivo |
| file ./* | Determina el tipo de archivo de **todos** los archivos del directorio |

## Referencias
[Manual linux (file)](https://man7.org/linux/man-pages/man1/file.1.html)
