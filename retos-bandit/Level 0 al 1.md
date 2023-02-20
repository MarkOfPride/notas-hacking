---
share: true
---
# Bandit Level 0 → Level 1

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado **readme** ubicado en el directorio home. Usa esta contraseña para entrar en bandit1 usando SSH. Siempre que encuentres una contraseña para un nivel, usa SSH (en el puerto 2220) para entrar en ese nivel y continuar el juego.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit0
bandit0

## Solución
```bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| cat | Muestra el contenido de un archivo |
| ls | Listar archivos |

## Referencias