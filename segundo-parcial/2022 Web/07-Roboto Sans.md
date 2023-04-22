# Roboto Sans

## Descripción
La bandera está en algún lugar de esta aplicación web, no necesariamente en el sitio web. Encuéntrela.
Mira [esto](http://saturn.picoctf.net:55771/)

## Pistas
- (None)

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:55771/robots.txt                      
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/                                                                                                          
┌──(kali㉿kali)-[~]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode('anMvbXlmaWxlLnR4dA==')
b'js/myfile.txt'
>>> exit()
                                                                                                          
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:55771/js/myfile.txt
picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}
```

## Bandera
picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| robots.txt | Indica a los rastreadores de los buscadores a qué URLs de tu sitio pueden acceder |
| base64.b64decode | Decodifica el objeto similar a bytes codificado en Base64 o cadena de caracteres ASCII s y retorna los bytes decodificados |

## Referencias
[Introducción a los archivos robots.txt](https://developers.google.com/search/docs/crawling-indexing/robots/intro?hl=es#:~:text=Cerrar%20Entendido-,Un%20archivo%20robots.,p%C3%A1gina%20web%20aparezca%20en%20Google.)
[base64](https://docs.python.org/es/3/library/base64.html)