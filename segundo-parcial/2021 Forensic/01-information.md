# information

## Descripción
Los archivos siempre pueden modificarse de forma secreta. ¿Puedes encontrar la bandera? [cat.jpg](https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg)
## Pistas
- Mira los detalles del archivo
- Asegúrese de enviar la bandera como picoCTF{XXXXX}

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/information]
└─$ exiftool cat.jpg
ExifTool Version Number         : 12.49
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 14:24:46-04:00
File Access Date/Time           : 2023:04:23 14:08:14-04:00
File Inode Change Date/Time     : 2023:04:20 13:51:40-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/information]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode("cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9")
b'picoCTF{the_m3tadata_1s_modified}'
>>> exit()
```

## Bandera
picoCTF{the_m3tadata_1s_modified}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| exiftool | Es una aplicación de línea de comandos para leer, escribir y editar metainformación en una amplia variedad de archivos |
| base64.b64decode | Decodifica el objeto similar a bytes codificado en Base64 o cadena de caracteres ASCII y retorna los bytes decodificados |

## Referencias
[exiftool](https://exiftool.org/index.html)
[base64](https://docs.python.org/es/3/library/base64.html)