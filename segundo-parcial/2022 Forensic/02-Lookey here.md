# Lookey here

## Descripción
Los atacantes han ocultado información en una gran masa de datos en el pasado, tal vez lo sigan haciendo.
Descargue los datos [aquí](https://artifacts.picoctf.net/c/126/anthem.flag.txt).

## Pistas
- Descargue el archivo y busque la bandera en función del prefijo conocido

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/Lookeyhere]
└─$ wget https://artifacts.picoctf.net/c/126/anthem.flag.txt
--2023-04-23 15:40:33--  https://artifacts.picoctf.net/c/126/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.34, 18.160.124.119, 18.160.124.38, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.34|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt                     100%[=================================================================>] 106.12K  --.-KB/s    in 0.1s    

2023-04-23 15:40:33 (875 KB/s) - ‘anthem.flag.txt’ saved [108668/108668]

                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/Lookeyhere]
└─$ cat anthem.flag.txt | grep pico
      we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}
```

## Bandera
picoCTF{gr3p_15_@w3s0m3_2116b979}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| grep | Imprime líneas que coincidan con un patrón |

## Referencias
[grep(1) - Linux man page](https://linux.die.net/man/1/grep)