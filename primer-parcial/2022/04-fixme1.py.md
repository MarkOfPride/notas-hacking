# fixme1.py

## Descripción
Corregir el error de sintaxis en este script Python para imprimir la bandera.
[Descargar script Python](https://artifacts.picoctf.net/c/26/fixme1.py)

## Pistas
- La sangría es muy importante en Python
- Para ver el archivo en el webshell, haga: `$ nano fixme1.py`
- Para salir de `nano`, pulsa Ctrl y x y sigue las instrucciones en pantalla
- La función `str_xor` no necesita ingeniería inversa para este reto

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/26/fixme1.py
--2023-03-25 01:23:34--  https://artifacts.picoctf.net/c/26/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.42, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                                            100%[=====================================================================================================================>]     837  --.-KB/s    in 0s      

2023-03-25 01:23:34 (39.8 MB/s) - 'fixme1.py' saved [837/837]

markofpride-picoctf@webshell:~$ nano fixme1.py 
markofpride-picoctf@webshell:~$ python3 fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
```

## Bandera
picoCTF{1nd3nt1ty_cr1515_09ee727a}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| python3 | Ejecuta código en lenguaje de programación python |
| nano | Sirve para editar texto |

En este caso el error era de identación en la última línea (una tabulación extra).

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[PYTHON](https://www.commandlinux.com/man-page/man1/python3.1.html)
[Comando nano](https://josesalazarpantoja.gitbooks.io/comandos-basicos-linux/content/comando-nano.html)