# What Lies Within

## Descripción
Hay algo en el [edificio](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). ¿Puedes recuperar la bandera?

## Pistas
- Hay datos codificados en alguna parte... podría haber un descodificador en línea.

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/WhatLiesWithin]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
```

## Bandera
picoCTF{h1d1ng_1n_th3_b1t5}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| zsteg | Detecta datos ocultos en PNG y BMP |
| grep | Imprime líneas que coincidan con un patrón |

## Referencias
[zsteg](https://github.com/zed-0xff/zsteg)
[grep(1) - Linux man page](https://linux.die.net/man/1/grep)