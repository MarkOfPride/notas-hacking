# shark on wire 2

## Descripción
Encontramos esta [captura de paquetes](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recupera la bandera que fue robada de la red.

## Pistas
- (None)

## Solución
La solución es un pequeño script de python que lee todos los paquetes de la captura  y obtiene solo los que vengan del puerto 22.

```python
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
	if UDP in p and p[UDP].dport == 22:
		if p[UDP].sport > 5000:
			flag += chr(p[UDP].sport - 5000)
print(flag)
```

## Bandera
picoCTF{p1LLf3r3d_data_v1a_st3g0}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| scapy | Es un potente programa y biblioteca de manipulación interactiva de paquetes basado en Python |

## Referencias
[Scapy](https://pypi.org/project/scapy/)