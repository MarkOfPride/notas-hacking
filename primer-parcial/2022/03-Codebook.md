# Codebook

## Descripción
Ejecute el script de Python `code.py` en el mismo directorio que `codebook.txt`.
- [Descargar code.py](https://artifacts.picoctf.net/c/1/code.py)
- [Descargar codebook.txt](https://artifacts.picoctf.net/c/1/codebook.txt)

## Pistas
- En el webshell, utilice `ls` para ver si ambos archivos están en el directorio en el que se encuentra
- La función `str_xor` no necesita ingeniería inversa para este reto

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/1/code.py
--2023-03-25 00:09:49--  https://artifacts.picoctf.net/c/1/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.120, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                              100%[=====================================================================================================================>]   1.25K  --.-KB/s    in 0s      

2023-03-25 00:09:49 (776 MB/s) - 'code.py' saved [1278/1278]

markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/1/codebook.txt
--2023-03-25 00:09:58--  https://artifacts.picoctf.net/c/1/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.120, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                         100%[=====================================================================================================================>]      27  --.-KB/s    in 0s      

2023-03-25 00:09:58 (27.1 MB/s) - 'codebook.txt' saved [27/27]

markofpride-picoctf@webshell:~$ ls
README.txt  code.py  codebook.txt  convertme.py  runme.py
markofpride-picoctf@webshell:~$ python3 code.py 
picoCTF{c0d3b00k_455157_d9aa2df2}
```

## Bandera
picoCTF{c0d3b00k_455157_d9aa2df2}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| ls | Listar el contenido del directorio |
| python3 | Ejecuta código en lenguaje de programación python |

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[ls(1) - Linux man page](https://linux.die.net/man/1/ls)
[PYTHON](https://www.commandlinux.com/man-page/man1/python3.1.html)
