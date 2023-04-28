# Wireshark doo dooo do doo...

## Descripción
¿Puedes encontrar la bandera? [shark1.pcapng](https://mercury.picoctf.net/static/ae5b2bc07928fca272ff3900dc9a6cef/shark1.pcapng)

## Pistas
- (None)

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/WiresharkDooDoooDoDoo]
└─$ wget https://mercury.picoctf.net/static/ae5b2bc07928fca272ff3900dc9a6cef/shark1.pcapng        
--2023-04-23 14:32:28--  https://mercury.picoctf.net/static/ae5b2bc07928fca272ff3900dc9a6cef/shark1.pcapng
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1558808 (1.5M) [application/octet-stream]
Saving to: ‘shark1.pcapng’

shark1.pcapng                       100%[=================================================================>]   1.49M  1.64MB/s    in 0.9s    

2023-04-23 14:32:30 (1.64 MB/s) - ‘shark1.pcapng’ saved [1558808/1558808]

                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/WiresharkDooDoooDoDoo]
└─$ wireshark shark1.pcapng &                                                             
[1] 8071
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/WiresharkDooDoooDoDoo]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> codecs.decode('Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}', 'rot_13')
'The flag is picoCTF{p33kab00_1_s33_u_deadbeef}'
>>> exit()

```

## Bandera
picoCTF{p33kab00_1_s33_u_deadbeef}

## Notas adicionales
La cadena cifrada en ROT13 se obtiene siguiendo el stream de los paquetes TCP, en el stream 5.

| Comando | Descripción |
|--------|--------|
| codecs.decode - ROT13 | Devuelve el cifrado César del operando |
| wireshark | Es un analizador de protocolos utilizado para realizar análisis y solucionar problemas en redes de comunicaciones, para análisis de datos y protocolos, y como una herramienta didáctica |

## Referencias
[codecs](https://docs.python.org/3/library/codecs.html)
[wireshark](https://es.wikipedia.org/wiki/Wireshark)
