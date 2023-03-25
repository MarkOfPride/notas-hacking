# shark on wire 1

## Descripción
Encontramos esta [captura de paquete](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recupera la bandera.

## Pistas
- Intenta usar una herramienta como Wireshark
- ¿Qué son los streams?

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/sharkonwire1]
└─$ wireshark capture.pcap &
[1] 1618
```

Seguimos cualquier UDP stream y nos movemos entre streams hasta encontrar la bandera (stream 6).

## Bandera
picoCTF{StaT31355_636f6e6e}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wireshark | Análisis en profundidad de TCP/IP |

## Referencias
[wireshark](https://www.wireshark.org/docs/)