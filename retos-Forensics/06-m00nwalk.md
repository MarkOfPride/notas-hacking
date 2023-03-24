# m00nwalk

## Descripción
Descifra este [mensaje](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) de la Luna.

## Pistas
- ¿Cómo se enviaron a la Tierra las imágenes del alunizaje?
- ¿Cuál es la mascota CMU?, que podría ayudar a seleccionar una opción RX

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/m00nwalk]
└─$ sstv -d message.wav -o resultado.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                          [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/m00nwalk]
└─$ ls
message.wav  resultado.png
                                                                                                                                                                             
┌──(kali㉿kali)-[~/picoctf/forensic/m00nwalk]
└─$ open resultado.png 
```

## Bandera
picoCTF{beep_boop_im_in_space}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| XXX | YYYYYYYY |

## Referencias