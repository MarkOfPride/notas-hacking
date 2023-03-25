# extensions

## Descripción
Este es un archivo de texto muy raro [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt) ¿Puedes encontrar la bandera?

## Pistas
- ¿Cómo saben los sistemas operativos qué tipo de archivo es? (¡No es sólo el final!)
- Asegúrese de enviar la bandera como picoCTF{XXXXX}

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/extensions]
└─$ mv flag.txt flag.png
                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensic/extensions]
└─$ ls
flag.png
                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensic/extensions]
└─$ open flag.png  
```

## Bandera
picoCTF{now_you_know_about_extensions}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| mv | mover (renombrar) archivos, tambien cambia la extensión de un archivo |

## Referencias
[mv(1) - Linux man page](https://linux.die.net/man/1/mv)