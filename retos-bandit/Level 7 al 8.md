# Bandit Level 7 → Level 8

## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo data.txt junto a la palabra **millionth**

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solución
```bash
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ wc data.txt
  98567  197133 4184396 data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| grep | Toma una expresión regular de la línea de comandos, lee la entrada estándar o una lista de archivos, e imprime las líneas que contengan coincidencias para la expresión regular. |

## Referencias
[Uso del comando grep](https://geekland.eu/uso-del-comando-grep-en-linux-y-unix-con-ejemplos/)