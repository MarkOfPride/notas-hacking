# caesar

## Descripción
Descifra este [mensaje](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext)

## Pistas
- [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher) de cifrado cesar

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
--2023-04-22 02:13:08--  https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 35 [application/octet-stream]
Saving to: 'ciphertext'

ciphertext                                           100%[=====================================================================================================================>]      35  --.-KB/s    in 0s      

2023-04-22 02:13:08 (16.7 MB/s) - 'ciphertext' saved [35/35]

markofpride-picoctf@webshell:~$ cat ciphertext 
picoCTF{ynkooejcpdanqxeykjrbdofgkq}
```

**Mensaje cifrado:** `ynkooejcpdanqxeykjrbdofgkq`

**Mensaje descifrado:** `crossingtherubiconvfhsjkou`

## Bandera
picoCTF{crossingtherubiconvfhsjkou}

## Notas adicionales
El conjunto de caracteres dado en el problema se decodificaron en **Cifrado César** usando la herramienta "CyberChef" para encontrar la bandera. En este caso se experimentaron con el número de rotaciones hasta encontrar texto legible, la cantidad correcta era 4.

>[!info]
>**Cifrado César**
>Es un tipo de cifrado por sustitución en el que una letra en el texto original es reemplazada por otra letra que se encuentra un número fijo de posiciones más adelante en el alfabeto.

## Referencias
[Cifrado César](https://es.wikipedia.org/wiki/Cifrado_C%C3%A9sar)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,4)&input=eW5rb29lamNwZGFucXhleWtqcmJkb2Zna3E)