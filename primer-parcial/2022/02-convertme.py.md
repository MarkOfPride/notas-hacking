# convertme.py

## Descripción
Ejecuta el script de Python y convierte el número dado de decimal a binario para obtener la bandera.
[Descargar script Python](https://artifacts.picoctf.net/c/24/convertme.py)

## Pistas
- Busca una aplicación de conversión de números decimales a binarios en Internet o utiliza la calculadora de tu ordenador
- La función `str_xor` no necesita ingeniería inversa para este reto
- Si tienes Python en tu ordenador, puedes descargar el script normalmente y ejecutarlo. Si no, utiliza el comando `wget` en la webshell
- Para utilizar `wget` en el webshell, primero haga clic con el botón derecho del ratón en el enlace de descarga y seleccione "Copiar enlace" o "Copiar dirección de enlace"
- Escriba todo después del signo de dólar en el webshell: `$ wget`, a continuación, pegue el enlace después del espacio después de `wget` y pulse enter. Esto descargará el script en el webshell para que puedas ejecutarlo
- Por último, para ejecutar la secuencia de comandos, escriba todo después del signo de dólar y pulse Intro: `$ python3 convertme.py`

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/24/convertme.py
--2023-03-25 00:02:10--  https://artifacts.picoctf.net/c/24/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                         100%[=====================================================================================================================>]   1.16K  --.-KB/s    in 0s      

2023-03-25 00:02:10 (534 MB/s) - 'convertme.py' saved [1189/1189]

markofpride-picoctf@webshell:~$ ls
README.txt  convertme.py  runme.py
markofpride-picoctf@webshell:~$ python3 convertme.py 
If 92 is in decimal base, what is it in binary base?
Answer: 1011100
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_722f6b39}
```

## Bandera
picoCTF{4ll_y0ur_b4535_722f6b39}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| python3 | Ejecuta código en lenguaje de programación python |

Para transformar el numero de decimal a binario se utilizó la herramienta "CyberChef"

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[PYTHON](https://www.commandlinux.com/man-page/man1/python3.1.html)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Decimal('Space',false)To_Binary('Space',3)&input=OTI)