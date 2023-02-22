# Bandit Level 10 → Level 11

## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt**, que contiene datos codificados en base64.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución
```bash
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ echo "hola mundo"
hola mundo
bandit10@bandit:~$ echo "hola mundo" | base64
aG9sYSBtdW5kbwo=
bandit10@bandit:~$ echo -n aG9sYSBtdW5kbwo= | base64 -d
hola mundo
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```


## Notas adicionales
| Comando | Descripción |
|--------|--------|
| base64 | Para codificar o descodificar la entrada/salida estándar o el contenido de cualquier archivo |
| base64 -d | Esta opción se utiliza para descodificar cualquier dato codificado de la entrada estándar o de cualquier archivo. |

## Referencias
[Bash base64 encode and decode](https://linuxhint.com/bash_base64_encode_decode/)