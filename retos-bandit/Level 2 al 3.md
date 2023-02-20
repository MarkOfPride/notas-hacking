# Bandit Level 2 → Level 3

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado **spaces in this filename** ubicado en el directorio raíz

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Solución
```bash
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

## Notas adicionales

## Referencias
[Espacios en el nombre del archivo](https://linuxhint.com/reference-filename-with-spaces-linux/)