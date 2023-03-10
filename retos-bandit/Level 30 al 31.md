# Bandit Level 30 → Level 31

## Objetivo
Hay un repositorio git en ssh://bandit30-git@localhost/home/bandit30-git/repo. La contraseña para el usuario bandit30-git es la misma que para el usuario bandit30.
Clone the repository and find the password for the next level.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit30
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solución
```bash
bandit30@bandit:~$ mktemp -d
/tmp/tmp.BgCb3VXqcJ
bandit30@bandit:~$ cd /tmp/tmp.BgCb3VXqcJ
bandit30@bandit:/tmp/tmp.BgCb3VXqcJ$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/tmp.BgCb3VXqcJ$ ls -la
total 124
drwx------   3 bandit30 bandit30   4096 Mar 10 03:20 .
drwxrwx-wt 243 root     root     114688 Mar 10 03:21 ..
drwxrwxr-x   3 bandit30 bandit30   4096 Mar 10 03:21 repo
bandit30@bandit:/tmp/tmp.BgCb3VXqcJ$ cd repo/
bandit30@bandit:/tmp/tmp.BgCb3VXqcJ/repo$ ls -la
total 16
drwxrwxr-x 3 bandit30 bandit30 4096 Mar 10 03:21 .
drwx------ 3 bandit30 bandit30 4096 Mar 10 03:20 ..
drwxrwxr-x 8 bandit30 bandit30 4096 Mar 10 03:21 .git
-rw-rw-r-- 1 bandit30 bandit30   30 Mar 10 03:21 README.md
bandit30@bandit:/tmp/tmp.BgCb3VXqcJ/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.BgCb3VXqcJ/repo$ git tag
secret
bandit30@bandit:/tmp/tmp.BgCb3VXqcJ/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| git tag | Crear, listar, eliminar o verificar un objeto de etiqueta firmado con GPG |
| git  | Muestra uno o varios objetos (blobs, árboles, etiquetas y commits) |

## Referencias
[Manual de git (tag)](https://git-scm.com/docs/git-tag)
[Manual de git (show)](https://git-scm.com/docs/git-show)