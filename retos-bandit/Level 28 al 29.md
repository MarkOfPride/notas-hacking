# Bandit Level 28 → Level 29

## Objetivo
Hay un repositorio git en ssh://bandit28-git@localhost/home/bandit28-git/repo. La contraseña para el usuario bandit28-git es la misma que para el usuario bandit28.
Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit28
AVanL161y9rsbcJIsFHuw35rjaOM19nR

## Solución
```bash
bandit28@bandit:~$ mktemp -d
/tmp/tmp.Ge1LX9WWKu
bandit28@bandit:~$ cd /tmp/tmp.Ge1LX9WWKu
bandit28@bandit:/tmp/tmp.Ge1LX9WWKu$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password:
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/tmp.Ge1LX9WWKu$ ls -la
total 124
drwx------   3 bandit28 bandit28   4096 Mar 10 02:29 .
drwxrwx-wt 211 root     root     114688 Mar 10 02:29 ..
drwxrwxr-x   3 bandit28 bandit28   4096 Mar 10 02:29 repo
bandit28@bandit:/tmp/tmp.Ge1LX9WWKu$ cd repo/
bandit28@bandit:/tmp/tmp.Ge1LX9WWKu/repo$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Mar 10 02:29 .
drwx------ 3 bandit28 bandit28 4096 Mar 10 02:29 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Mar 10 02:29 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Mar 10 02:29 README.md
bandit28@bandit:/tmp/tmp.Ge1LX9WWKu/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/tmp.Ge1LX9WWKu/repo$ git log
commit 104db85a904e9691ff22aafe1a96124c88f75afa (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    fix info leak

commit 6c3c5e485cc531e5d52c321587ce1103833ab7c3
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    add missing data

commit cd3b97ef95879ec34df0d6c82f2a96d552f0e56c
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    initial commit of README.md
bandit28@bandit:/tmp/tmp.Ge1LX9WWKu/repo$ git checkout 6c3c5e485cc531e5d52c321587ce1103833ab7c3
Previous HEAD position was 104db85 fix info leak
HEAD is now at 6c3c5e4 add missing data
bandit28@bandit:/tmp/tmp.Ge1LX9WWKu/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| git log | Enumera las confirmaciones a las que se puede llegar siguiendo los enlaces padre desde la confirmación o confirmaciones dadas, pero excluye las confirmaciones a las que se puede llegar desde la confirmación o confirmaciones dadas con un ^ delante. |
| git checkout | Cambiar de rama o restaurar archivos del árbol de trabajo |

## Referencias
[Manual de git](https://git-scm.com/docs)