# WebNet1

## Descripción
Encontramos esta [captura de paquete](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) y la [clave](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recupera la bandera.

## Pistas
- Prueba a usar una herramienta como Wireshark
- ¿Cómo descifrar el flujo TLS?

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/WebNet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2023-03-31 23:24:47--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                  100%[===============================================>]  90.36K  --.-KB/s    in 0.1s    

2023-03-31 23:24:47 (889 KB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/WebNet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2023-03-31 23:24:56--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                  100%[===============================================>]   1.66K  --.-KB/s    in 0s      

2023-03-31 23:24:56 (42.3 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/WebNet1]
└─$ ls
capture.pcap  picopico.key
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/forensic/WebNet1]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2                                     
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
--
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
--
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
--
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_
                                                                        
```

## Bandera
picoCTF{honey.roasted.peanuts}

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