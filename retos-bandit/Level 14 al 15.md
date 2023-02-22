# Bandit Level 14 → Level 15

## Objetivo
La contraseña para el siguiente nivel se puede recuperar enviando la contraseña del nivel actual al **puerto 30000 en localhost**.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solución
```bash
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| nc | Permite la conexión a los puertos TCP/UDP de un host |

## Referencias
[Comando nc (netcat): Qué es y cómo se usa](https://www.neoguias.com/comando-nc/)