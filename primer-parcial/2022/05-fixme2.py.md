# fixme2.py

## Descripción
Corregir el error de sintaxis en el script Python para imprimir la bandera.
[Descargar script Python](https://artifacts.picoctf.net/c/5/fixme2.py)

## Pistas
- ¿Igualdad y asignación son el mismo símbolo?
- Para ver el archivo en el webshell, haga: `$ nano fixme2.py`
- Para salir de `nano`, pulsa Ctrl y x y sigue las instrucciones en pantalla.
- La función `str_xor` no necesita ingeniería inversa para este reto.

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/5/fixme2.py
--2023-03-25 01:33:41--  https://artifacts.picoctf.net/c/5/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                                            100%[=====================================================================================================================>]   1.00K  --.-KB/s    in 0s      

2023-03-25 01:33:41 (588 MB/s) - 'fixme2.py' saved [1029/1029]

markofpride-picoctf@webshell:~$ nano fixme2.py 
markofpride-picoctf@webshell:~$ python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

## Bandera
picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| python3 | Ejecuta código en lenguaje de programación python |
| nano | Sirve para editar texto |

En este caso el error era en la comparación ya que se usaba un signo de asignación `=` y no de comparación `==`.

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[PYTHON](https://www.commandlinux.com/man-page/man1/python3.1.html)
[Comando nano](https://josesalazarpantoja.gitbooks.io/comandos-basicos-linux/content/comando-nano.html)