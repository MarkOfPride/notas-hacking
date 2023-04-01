# Matryoshka doll

## Descripción
Las matrioskas son un conjunto de muñecas de madera de tamaño decreciente colocadas una dentro de otra. ¿Cuál es la última? [Imagen](https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg)

## Pistas
- Espera, ¿puedes esconder archivos dentro de archivos? ¿Pero cómo se encuentran?
- Asegúrese de enviar la bandera como picoCTF{XXXXX}

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/Matryoshkadoll]
└─$ wget https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg              
--2023-04-01 00:02:33--  https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651622 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg                     100%[===============================================>] 636.35K   101KB/s    in 5.3s    

2023-04-01 00:02:38 (120 KB/s) - ‘dolls.jpg’ saved [651622/651622]

                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/Matryoshkadoll]
└─$ open dolls.jpg 
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/Matryoshkadoll]
└─$ binwalk dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/Matryoshkadoll]
└─$ binwalk -e dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/Matryoshkadoll]
└─$ ls
dolls.jpg  _dolls.jpg.extracted
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/Matryoshkadoll]
└─$ cd _dolls.jpg.extracted 
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/Matryoshkadoll/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/Matryoshkadoll/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                                                                      
┌──(kali㉿kali)-[~/…/forensic/Matryoshkadoll/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                                                      
┌──(kali㉿kali)-[~/…/forensic/Matryoshkadoll/_dolls.jpg.extracted/base_images]
└─$ open 2_c.jpg  
                                                                                                                      
┌──(kali㉿kali)-[~/…/forensic/Matryoshkadoll/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg
383804        0x5DB3C         End of Zip archive, footer length: 22
383915        0x5DBAB         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/…/forensic/Matryoshkadoll/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                                                                      
┌──(kali㉿kali)-[~/…/forensic/Matryoshkadoll/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted  
                                                                                                                      
┌──(kali㉿kali)-[~/…/Matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ ls
2DD3B.zip  base_images
                                                                                                                      
┌──(kali㉿kali)-[~/…/Matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd base_images       
                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg
                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ open 3_c.jpg  
                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77650, uncompressed size: 79806, name: base_images/4_c.jpg
201422        0x312CE         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted 
                                                                                                                      
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ ls
1E2D6.zip  base_images
                                                                                                                      
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd base_images       
                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ open 4_c.jpg 
                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 62, uncompressed size: 81, name: flag.txt
79784         0x137A8         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg  _4_c.jpg.extracted
                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                                                                      
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                                                      
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt         
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}
```

## Bandera
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| binwalk | Es una herramienta que permite buscar en una imagen binaria archivos incrustados y código ejecutable |
| binwalk -e | Extraer automáticamente los tipos de archivo conocidos |

## Referencias
[binwalk Usage Example](https://www.kali.org/tools/binwalk/)
