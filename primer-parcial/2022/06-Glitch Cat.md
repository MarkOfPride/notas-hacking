# Glitch Cat

## Descripción
Nuestro servicio de impresión de banderas ha empezado a fallar.
`$ nc saturn.picoctf.net 50561`

## Pistas
- ASCII es una de las codificaciones más utilizadas en programación
- Sabemos que la salida del glitch es Python válido, ¡de alguna manera!
- Pulse Ctrl y c en el teclado para cerrar la conexión y volver al símbolo del sistema

## Solución
```bash
markofpride-picoctf@webshell:~$ nc saturn.picoctf.net 50561
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
^C
```

## Bandera
picoCTF{gl17ch_m3_n07_9c42a45d}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| nc | La utilidad nc (o netcat) se utiliza para casi cualquier cosa bajo el sol que implique TCP o UDP |

Se utilizó la herramienta "CyberChef" para pasar los caracteres de hexadecimal a ASCII

## Referencias
[nc(1) - Linux man page](https://linux.die.net/man/1/nc)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg2NA)
