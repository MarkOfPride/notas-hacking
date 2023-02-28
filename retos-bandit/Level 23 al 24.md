# Bandit Level 23 → Level 24

## Objetivo
Un programa se está ejecutando automáticamente a intervalos regulares desde cron, el programador de trabajos basado en el tiempo. Busque en /etc/cron.d/ la configuración y vea qué comando se está ejecutando.
**NOTA:** Este nivel requiere que crees tu primer shell-script. Este es un gran paso y debes estar orgulloso de ti mismo cuando superes este nivel.
**NOTA 2**: Tenga en cuenta que su script de shell se elimina una vez ejecutado, por lo que es posible que desee conservar una copia...

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit23
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solución
```bash
bandit23@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ mkdir /tmp/rsm02
bandit23@bandit:~$ cd /tmp/rsm02
bandit23@bandit:/tmp/rsm02$ nano rsmscript.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/rsm02$ chmod 777 rsmscript.sh
bandit23@bandit:/tmp/rsm02$ cat rsmscript.sh
cat /etc/bandit_pass/bandit24 > /tmp/rsm02/password
bandit23@bandit:/tmp/rsm02$ touch password
bandit23@bandit:/tmp/rsm02$ chmod 666 password
bandit23@bandit:/tmp/rsm02$ ls -la
total 112
drwxrwxr-x    2 bandit23 bandit23   4096 Feb 28 18:33 .
drwxrwx-wt 3010 root     root     106496 Feb 28 18:33 ..
-rw-rw-rw-    1 bandit23 bandit23      0 Feb 28 18:33 password
-rwxrwxrwx    1 bandit23 bandit23     52 Feb 28 18:32 rsmscript.sh
bandit23@bandit:/tmp/rsm02$ cp rsmscript.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/rsm02$ ls -la
total 116
drwxrwxr-x    2 bandit23 bandit23   4096 Feb 28 18:33 .
drwxrwx-wt 3010 root     root     106496 Feb 28 18:36 ..
-rw-rw-rw-    1 bandit23 bandit23     33 Feb 28 18:36 password
-rwxrwxrwx    1 bandit23 bandit23     52 Feb 28 18:32 rsmscript.sh
bandit23@bandit:/tmp/rsm02$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| mkdir | Crea directorios o carpetas |
| chmod | Cambia los permisos de un archivo |
| touch | Crea un archivo |
| cp | Copia un archivo a un directorio especificado |

## Referencias
[How to Write a Bash Script](https://www.datacamp.com/tutorial/how-to-write-bash-script-tutorial)