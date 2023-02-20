# Bandit Level 8 → Level 9

## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** y es la única línea de texto que aparece una sola vez

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Solución
```bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
 1001  1001 33033 data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| Pipe | Envia el output de un comando como input de otro |

## Referencias
[Piping](https://ryanstutorials.net/linuxtutorial/piping.php)