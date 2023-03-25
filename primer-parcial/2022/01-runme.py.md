# runme.py

## Descripción
Ejecuta el script `runme.py` para obtener la bandera. Descarga el script con tu navegador o con `wget` en el webshell.
[Descargar script runme.py Python](https://artifacts.picoctf.net/c/34/runme.py)

## Pistas
- Si tienes Python en tu ordenador, puedes descargar el script normalmente y ejecutarlo. Si no, utiliza el comando `wget` en la webshell
- Para utilizar `wget` en el webshell, primero haga clic con el botón derecho del ratón en el enlace de descarga y seleccione "Copiar enlace" o "Copiar dirección de enlace"
- Escriba todo después del signo de dólar en el webshell: `$ wget`, luego pegue el enlace después del espacio después de `wget` y presione enter. Esto descargará el script en el webshell para que puedas ejecutarlo
- Por último, para ejecutar el script, escribe todo lo que hay después del signo del dólar y pulsa intro: `$ python3 runme.py` ¡Ya deberías tener la bandera!

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2023-03-24 23:53:12--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.120, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                             100%[=====================================================================================================================>]     270  --.-KB/s    in 0s      

2023-03-24 23:53:12 (99.8 MB/s) - 'runme.py' saved [270/270]

markofpride-picoctf@webshell:~$ ls
README.txt  runme.py
markofpride-picoctf@webshell:~$ python3 runme.py 
picoCTF{run_s4n1ty_run}
```

## Bandera
picoCTF{run_s4n1ty_run}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| python3 | Ejecuta código en lenguaje de programación python |

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[PYTHON](https://www.commandlinux.com/man-page/man1/python3.1.html)

