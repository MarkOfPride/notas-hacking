# Bandit Level 18 → Level 19

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo readme en el homedirectory. Desafortunadamente, alguien ha modificado .bashrc para cerrar la sesión cuando te conectas con SSH

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit18
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Solución
```bash
C:\Users\Ricardo>ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:

awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

## Notas adicionales
Cuando se escribe un comando despues de la solicitud ssh este se ejecuta apenas te conectas.

## Referencias