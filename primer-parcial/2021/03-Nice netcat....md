# Nice netcat...

## Descripción
Hay un bonito programa con el que puedes hablar utilizando este comando en un intérprete de comandos: `$ nc mercury.picoctf.net 7449`, pero no habla inglés...

## Pistas
- Puedes practicar el uso de netcat con este problema de picoGym: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
- Puedes practicar la lectura y escritura ASCII con este problema de picoGym: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Solución
```bash
markofpride-picoctf@webshell:~$ nc mercury.picoctf.net 7449
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
102 
50 
100 
55 
99 
97 
102 
97 
125 
10 
^C
```

## Bandera
picoCTF{g00d_k1tty_n1c3_k1tty_f2d7cafa}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| nc | La utilidad nc (o netcat) se utiliza para casi cualquier cosa bajo el sol que implique TCP o UDP |
Los numeros resultantes del comando son el número de los caracteres ASCII de la bandera por lo que se usó la página "Texto - Ascii Converter / Translator" como herramienta para decodificar el mensaje.

## Referencias
[nc(1) - Linux man page](https://linux.die.net/man/1/nc)
[Texto - Ascii Converter / Translator](https://es.rakko.tools/tools/76/)
