# Packets Primer

## Descripción
Descargue el archivo de captura de paquetes y utilice un software de análisis de paquetes para encontrar la bandera.
- [Descargar captura de paquetes](https://artifacts.picoctf.net/c/196/network-dump.flag.pcap)

## Pistas
- Wireshark, si puedes instalarlo y usarlo, es probablemente el producto de software de análisis de paquetes más fácil de usar para principiantes

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/PacketsPrimer]
└─$ wget https://artifacts.picoctf.net/c/196/network-dump.flag.pcap
--2023-04-23 15:46:07--  https://artifacts.picoctf.net/c/196/network-dump.flag.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.34, 18.160.124.38, 18.160.124.119, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.34|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 778 [application/octet-stream]
Saving to: ‘network-dump.flag.pcap’

network-dump.flag.pcap              100%[=================================================================>]     778  --.-KB/s    in 0s      

2023-04-23 15:46:08 (16.1 MB/s) - ‘network-dump.flag.pcap’ saved [778/778]

                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/PacketsPrimer]
└─$ wireshark network-dump.flag.pcap &                             
[1] 26375
```

## Bandera
picoCTF{p4ck37_5h4rk_01b0a0d6}

## Notas adicionales
La bandera se encuentra al seguir el stream de cualquiera de los paquetes con protocolo TCP.

| Comando | Descripción |
|--------|--------|
| wireshark | es un analizador de protocolos utilizado para realizar análisis y solucionar problemas en redes de comunicaciones, para análisis de datos y protocolos, y como una herramienta didáctica |

## Referencias
[Wireshark](https://es.wikipedia.org/wiki/Wireshark)