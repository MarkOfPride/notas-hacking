# Bandit Level 6 → Level 7

## Objetivo
La contraseña para el siguiente nivel se almacena en algún lugar del servidor y tiene todas las propiedades siguientes:
- Propiedad del usuario bandit7
- Propiedad del grupo bandit6
- 33 bytes de tamaño

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Solución
```bash
bandit6@bandit:~$ ls
bandit6@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Jan 11 19:18 .
drwxr-xr-x 70 root root 4096 Jan 11 19:19 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2</dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| ls -la | Retorna una lista detallada de **todos** los elementos |
| find -user | Busca los archivos por usuario |
| find -group | Busca los archivos por grupo |
| 2</dev/null | Quita los mensajes de error |

## Referencias
[Manual linux (find)](https://man7.org/linux/man-pages/man1/find.1.html)