# Bandit Level 27 → Level 28

## Objetivo
Hay un repositorio git en ssh://bandit27-git@localhost/home/bandit27-git/repo. La contraseña para el usuario bandit27-git es la misma que para el usuario bandit27.
Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solución
```bash
bandit27@bandit:~$ mktemp -d
/tmp/tmp.F9y2BGRf42
bandit27@bandit:~$ cd /tmp/tmp.F9y2BGRf42
bandit27@bandit:/tmp/tmp.F9y2BGRf42$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/tmp.F9y2BGRf42$ ls -la
total 120
drwx------    3 bandit27 bandit27   4096 Feb 28 19:28 .
drwxrwx-wt 3078 root     root     110592 Feb 28 19:28 ..
drwxrwxr-x    3 bandit27 bandit27   4096 Feb 28 19:28 repo
bandit27@bandit:/tmp/tmp.F9y2BGRf42$ cd repo
bandit27@bandit:/tmp/tmp.F9y2BGRf42/repo$ ls -la
total 16
drwxrwxr-x 3 bandit27 bandit27 4096 Feb 28 19:28 .
drwx------ 3 bandit27 bandit27 4096 Feb 28 19:28 ..
drwxrwxr-x 8 bandit27 bandit27 4096 Feb 28 19:28 .git
-rw-rw-r-- 1 bandit27 bandit27   68 Feb 28 19:28 README
bandit27@bandit:/tmp/tmp.F9y2BGRf42/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| mktemp | Permite crear archivos o directorios temporales |
| git clone | Se utiliza para copiar un repositorio Git existente en un nuevo directorio local |

## Referencias
[Comando mktemp de Linux para principiantes](https://howtoforge.es/tutorial-del-comando-mktemp-de-linux-para-principiantes-5-ejemplos/)
[Git Clone](https://www.gitkraken.com/learn/git/git-clone#:~:text=Git%20clone%20is%20used%20to,checkout%20an%20initial%20branch%20locally.)