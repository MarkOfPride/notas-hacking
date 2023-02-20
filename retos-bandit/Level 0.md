# Level 0

## Objetivo
El objetivo de este nivel es que te conectes al juego usando SSH. El host al que necesitas conectarte es **bandit.labs.overthewire.org**, en el puerto 2220. El nombre de usuario es **bandit0** y la contraseña es **bandit0**. Una vez conectado, ve a la página [Nivel 1](https://overthewire.org/wargames/bandit/bandit1.html) para averiguar cómo superar el Nivel 1.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit0
bandit0

## Solución
```bash
C:\Users\Ricardo>ssh bandit0@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit0@bandit.labs.overthewire.org's password:
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| SSH | Nos permite conectarnos a una maquina remota y ejecutar comandos |

## Referencias
[SSH](https://en.wikipedia.org/wiki/Secure_Shell)