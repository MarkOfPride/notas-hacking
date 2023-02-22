# Level X

## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt**, que es un hexdump de un archivo que ha sido comprimido repetidamente. Para este nivel puede ser útil crear un directorio bajo /tmp en el que puedas trabajar usando mkdir. Por ejemplo: mkdir /tmp/myname123. Luego copie el archivo de datos usando cp, y renómbrelo usando mv (¡lea las páginas de manual!)

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solución
```bash
bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Tue Feb 21 22:02:52 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| xxd | Crea un volcado hexadecimal de un archivo. También puede convertir un volcado hexadecimal de nuevo a su forma binaria inicial. |
| xxd -r | Transforma de hexadecimal a binario |
| zcat | Es una utilidad de línea de comandos para ver el contenido de un archivo comprimido sin descomprimirlo literalmente |
| bzcat | Imprime archivos en stdout |
| tar xO | Escribe los archivos extraídos en la salida estándar, en lugar de crear los archivos en el sistema de archivos |



## Referencias
[Hex dump](https://en.wikipedia.org/wiki/Hex_dump)
[xxd](https://francisconi.org/linux/comandos/xxd)
[Ejemplos de comandos zcat de Linux para principiantes](https://es.linux-console.net/?p=2219#gsc.tab=0)
[bzip2](https://www.commandlinux.com/man-page/man1/bzcat.1.html)
[GNU tar: an archiver tool](https://www.gnu.org/software/tar/manual/tar.html#SEC86)


