# Bandit Level 13 → Level 14

## Objetivo
La contraseña para el siguiente nivel se almacena en **/etc/bandit_pass/bandit14 y sólo puede ser leída por el usuario bandit14**. Para este nivel, no obtienes la siguiente contraseña, pero obtienes una clave SSH privada que puede ser usada para iniciar sesión en el siguiente nivel. **Nota: localhost** es un nombre de host que se refiere a la máquina en la que estás trabajando.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit13
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Solución
```bash
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? Yes
```
```bash
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$ exit
logout
Connection to localhost closed.
bandit13@bandit:~$ exit
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| localhost | Nombre de host que se refiere a la máquina en la que está trabajando |

## Referencias