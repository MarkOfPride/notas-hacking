# Bandit Level 20 → Level 21

## Objetivo
Hay un binario setuid en el homedirectory que hace lo siguiente: establece una conexión con localhost en el puerto que especifiques como argumento en la línea de comandos. Luego lee una línea de texto de la conexión y la compara con la contraseña del nivel anterior (bandit20). Si la contraseña es correcta, transmitirá la contraseña para el siguiente nivel (bandit21).
**NOTA:** Prueba a conectarte a tu propio demonio de red para ver si funciona como crees.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solución
```bash
bandit20@bandit:~$ nc -lnvp 2023 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 141208
bandit20@bandit:~$ Listening on 0.0.0.0 2023

bandit20@bandit:~$ ./suconnect 2023
Connection received on 127.0.0.1 47742
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -lnvp 2023 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| nc -lnvp | Permite que una misma maquina sea host y conexión |
| & | Manda las ejecuciones a segundo plano |

## Referencias
