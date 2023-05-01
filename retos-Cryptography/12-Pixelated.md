# Pixelated

## Descripción
Tengo estas 2 imágenes, ¿puedes hacer una bandera con ellas? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)
## Pistas
- https://en.wikipedia.org/wiki/Visual_cryptography
- Piensa en distintas formas de "apilar" imágenes

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/cryptography/Pixelated]
└─$ wget https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png
--2023-04-30 22:00:59--  https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png              100%[===========================================>] 192.55K   962KB/s    in 0.2s    

2023-04-30 22:01:00 (962 KB/s) - ‘scrambled1.png’ saved [197173/197173]

                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/Pixelated]
└─$ wget https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png
--2023-04-30 22:01:20--  https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197172 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png              100%[===========================================>] 192.55K   932KB/s    in 0.2s    

2023-04-30 22:01:20 (932 KB/s) - ‘scrambled2.png’ saved [197172/197172]

                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/Pixelated]
└─$ nano exp.py                            
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/Pixelated]
└─$ cat exp.py
from PIL import Image
import numpy as np

image1 = np.asarray( Image.open('scrambled1.png') )
image2 = np.asarray( Image.open('scrambled2.png') )

data = image1.copy() + image2.copy()

new = Image.fromarray(data)

new.save('new.png', 'PNG')
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/Pixelated]
└─$ python3 exp.py
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/Pixelated]
└─$ ls
exp.py  new.png  scrambled1.png  scrambled2.png
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/Pixelated]
└─$ open new.png  
```

## Bandera
picoCTF{2a4d45c7}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| PIL | Biblioteca adicional gratuita y de código abierto para el lenguaje de programación Python que agrega soporte para abrir, manipular y guardar muchos formatos de archivo de imagen diferentes |
| numpy | Biblioteca para el lenguaje de programación Python que da soporte para crear vectores y matrices grandes multidimensionales, junto con una gran colección de funciones matemáticas de alto nivel para operar con ellas |

>[!info]
>**Criptografía visual**
>Es una técnica criptográfica que permite cifrar información visual (imágenes, texto, etc.) de manera que la información descifrada aparezca como una imagen visual.

## Referencias
[Pillow (biblioteca de código abierto)](https://es.wikipedia.org/wiki/Pillow_(biblioteca_de_c%C3%B3digo_abierto))
[NumPy](https://es.wikipedia.org/wiki/NumPy)
[Visual cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)

