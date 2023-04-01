# tunn3l v1s10n

## Descripción
Encontramos este [archivo](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recuperar la bandera.

## Pistas
- Es raro que no se muestre bien...

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/tunn3lv1s10n]
└─$ wget https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n
--2023-04-01 00:14:01--  https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2893454 (2.8M) [application/octet-stream]
Saving to: ‘tunn3l_v1s10n’

tunn3l_v1s10n                 100%[===============================================>]   2.76M  53.7KB/s    in 50s     

2023-04-01 00:14:51 (56.7 KB/s) - ‘tunn3l_v1s10n’ saved [2893454/2893454]

                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/tunn3lv1s10n]
└─$ ls
tunn3l_v1s10n
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/tunn3lv1s10n]
└─$ file tunn3l_v1s10n 
tunn3l_v1s10n: data
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/tunn3lv1s10n]
└─$ hexeditor tunn3l_v1s10n 
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/tunn3lv1s10n]
└─$ open tunn3l_v1s10n 
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/tunn3lv1s10n]
└─$ hexeditor tunn3l_v1s10n
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/tunn3lv1s10n]
└─$ open tunn3l_v1s10n
```

## Bandera
picoCTF{qu1t3_a_v13w_2020}

## Notas adicionales
Para solucionar este reto se utilizó el editor hexadecimal para corregir detalles del encabezado del archivo, en este caso un BMP y luego se jugó cambiando el alto de la imagen para encontrar la bandera, (se modificó el offset 16).

## Referencias
[BMP file format](https://en.wikipedia.org/wiki/BMP_file_format)