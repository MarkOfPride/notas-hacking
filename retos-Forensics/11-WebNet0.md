# WebNet0

## Descripción
Encontramos esta [captura de paquete](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) y la [clave](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recupera la bandera.

## Pistas
- Intenta usar una herramienta como Wireshark
- ¿Cómo descifrar el flujo TLS?

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/WebNet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
--2023-03-31 22:44:56--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13163 (13K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                  100%[===============================================>]  12.85K  --.-KB/s    in 0s      

2023-03-31 22:44:57 (426 MB/s) - ‘capture.pcap’ saved [13163/13163]

                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/WebNet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
--2023-03-31 22:45:08--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                  100%[===============================================>]   1.66K  --.-KB/s    in 0s      

2023-03-31 22:45:08 (51.0 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/WebNet0]
└─$ ls
capture.pcap  picopico.key
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/WebNet0]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2
    61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67    ag: picoCTF{nong
    73 68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63    shim.shrimp.crac
    6b 65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c    kers}..Content-L
--
    67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73    g: picoCTF{nongs
    68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63 6b    him.shrimp.crack
    65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c 65    ers}..Content-Le
```

## Bandera
picoCTF{nongshim.shrimp.crackers}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| ssldump | Volcar el tráfico SSL en una red |
| ssldump -r | Especifica el dumpfile |
| ssldump -k | Especifica el keyfile |
| ssldump -d | Visualizar el tráfico de datos de la aplicación |

## Referencias
[ssldump(1) - Linux man page](https://linux.die.net/man/1/ssldump)
[Transport Layer Security (TLS)](https://en.wikipedia.org/wiki/Transport_Layer_Security)