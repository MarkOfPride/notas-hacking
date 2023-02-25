# Bandit Level 17 → Level 18

## Objetivo
Hay 2 archivos en el homedirectory: **passwords.old y passwords.new**. La contraseña para el siguiente nivel está en **passwords.new** y es la única línea que ha cambiado entre **passwords.old y passwords.new**
**NOTA: si has resuelto este nivel y ves 'Byebye!' al intentar entrar en bandit18, esto está relacionado con el siguiente nivel, bandit19**

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

## Solución
```bash
bandit17@bandit:~$ ls -ls
total 8
4 -rw-r----- 1 bandit18 bandit17 3300 Feb 21 22:02 passwords.new
4 -rw-r----- 1 bandit18 bandit17 3300 Feb 21 22:02 passwords.old
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< f9wS9ZUDvZoo3PooHgYuuWdawDFvGld2
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| diff | Es la utilidad para comparar directorios entre si o ficheros entre sí |
| --color | Da color a la consola |

## Referencias
[Comparar directorios y archivos con el comando diff en Linux](https://geekland.eu/comparar-directorios-y-archivos-comando-diff-linux/)
