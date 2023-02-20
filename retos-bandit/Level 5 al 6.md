# Bandit Level 5 → Level 6

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo en algún lugar bajo el directorio **inhere** y tiene todas las siguientes propiedades:
- Legible para el ser humano
- 1033 bytes de tamaño
- No ejecutable

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Solución
```bash
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find . -readable -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| find | Busca archivos en una jerarquía de directorios |
| find -readable | Coincide con los archivos que puede leer el usuario actual |
| find -type | Define el tipo del fichero |
| find -size | Define el tamaño del fichero |

## Referencias
[Manual linux (find)](https://man7.org/linux/man-pages/man1/find.1.html)