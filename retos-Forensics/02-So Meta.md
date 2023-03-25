# So Meta

## Descripción
Encuentra la bandera en esta [imagen](https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png).

## Pistas
- ¿Qué significa meta en el contexto de los archivos?
- ¿Ha oído hablar de los metadatos?

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/SoMeta]
└─$ exiftool pico_img.png | grep pico
File Name                       : pico_img.png
Artist                          : picoCTF{s0_m3ta_eb36bf44}
```

## Bandera
picoCTF{s0_m3ta_eb36bf44}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| exiftool | Lee y escribe metainformación en archivos |
| grep | Imprime líneas que coincidan con un patrón |

## Referencias
[exiftool(1) - Linux man page](https://linux.die.net/man/1/exiftool)
[grep(1) - Linux man page](https://linux.die.net/man/1/grep)

