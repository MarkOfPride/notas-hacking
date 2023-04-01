# c0rrupt

## Descripción
Encontramos este [archivo](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recuperar la bandera.

## Pistas
- Intenta arreglar la cabecera del archivo

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
--2023-03-31 22:00:43--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 202940 (198K) [application/octet-stream]
Saving to: ‘mystery’

mystery           100%[==========>] 198.18K   901KB/s    in 0.2s    

2023-03-31 22:00:43 (901 KB/s) - ‘mystery’ saved [202940/202940]

                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ ls
mystery
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ file mystery                                             
mystery: data
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ hexeditor mystery
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ file mystery     
mystery: data
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ pngcheck mystery 
zlib warning:  different version (expected 1.2.13, using 1.2.11)

mystery:  invalid chunk name \"C"DR" (43 22 44 52)
ERROR: mystery
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ hexeditor mystery
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ file mystery     
mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ pngcheck mystery 
zlib warning:  different version (expected 1.2.13, using 1.2.11)

mystery  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERROR: mystery
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ hexeditor mystery  
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.2.11)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ hexeditor mystery  
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.2.11)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ hexeditor mystery  
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.2.11)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).
                                                                     
┌──(kali㉿kali)-[~/picoctf/forensic/c0rrupt]
└─$ open mystery 

```

## Bandera
picoCTF{c0rrupt10n_1847995}

## Notas adicionales
Mucha teoria acerca de las imagenes png en las referencias se deja un link para comprender como funciona por dentro este tipo de archivo.

| Comando | Descripción |
|--------|--------|
| hexeditor | Editor de archivos hexadecimal |
| pngcheck | Verifica la integridad de los archivos PNG, JNG y MNG |

## Referencias
[pngcheck](http://www.libpng.org/pub/png/apps/pngcheck.html)
[PNG](https://en.wikipedia.org/wiki/PNG)