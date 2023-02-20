# Bandit Level 3 → Level 4

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo oculto en el directorio **inhere**.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit3
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Solución
```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| ls -a | No ignora la las entradas que empiezan con punto |

## Referencias
[Manual linux (ls)](https://man7.org/linux/man-pages/man1/ls.1.html)