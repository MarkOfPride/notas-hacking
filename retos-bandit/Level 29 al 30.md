# Bandit Level 29 → Level 30

## Objetivo
Hay un repositorio git en ssh://bandit29-git@localhost/home/bandit29-git/repo. La contraseña para el usuario bandit29-git es la misma que para el usuario bandit29.
Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit29
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solución
```bash
bandit29@bandit:~$ mktemp -d
/tmp/tmp.w1NtCNJ5Re
bandit29@bandit:~$ cd /tmp/tmp.w1NtCNJ5Re
bandit29@bandit:/tmp/tmp.w1NtCNJ5Re$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
Receiving objects: 100% (16/16), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tmp.w1NtCNJ5Re$ ls -la
total 124
drwx------   3 bandit29 bandit29   4096 Mar 10 02:41 .
drwxrwx-wt 223 root     root     114688 Mar 10 02:42 ..
drwxrwxr-x   3 bandit29 bandit29   4096 Mar 10 02:42 repo
bandit29@bandit:/tmp/tmp.w1NtCNJ5Re$ cd repo/
bandit29@bandit:/tmp/tmp.w1NtCNJ5Re/repo$ ls -la
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Mar 10 02:42 .
drwx------ 3 bandit29 bandit29 4096 Mar 10 02:41 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Mar 10 02:42 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Mar 10 02:42 README.md
bandit29@bandit:/tmp/tmp.w1NtCNJ5Re/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.w1NtCNJ5Re/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/dev
  origin/master
  origin/sploits-dev
bandit29@bandit:/tmp/tmp.w1NtCNJ5Re/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/tmp.w1NtCNJ5Re/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| git branch -r | Lista o elimina (si se utiliza con -d) las ramas de seguimiento remoto. Combinar con --list para que coincida con el patrón o patrones opcionales. |

## Referencias
[Manual de git (Branch)](https://git-scm.com/docs/git-branch)