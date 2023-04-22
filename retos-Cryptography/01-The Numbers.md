# The Numbers

## Descripción
Los [números](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... ¿qué significan?

## Pistas
- La bandera tiene el formato PICOCTF{}

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/cryptography/TheNumbers]
└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
--2023-04-20 14:17:29--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100721 (98K) [application/octet-stream]
Saving to: ‘the_numbers.png’

the_numbers.png            100%[======================================>]  98.36K   270KB/s    in 0.4s    

2023-04-20 14:17:42 (270 KB/s) - ‘the_numbers.png’ saved [100721/100721]

                                                                                                          
┌──(kali㉿kali)-[~/picoctf/cryptography/TheNumbers]
└─$ open the_numbers.png 
```

## Bandera
PICOCTF{thenumbersmason}

## Notas adicionales
El conjunto de número dado en la imagen del problema se decodificaron en **A1Z26** usando la herramienta "CyberChef" para encontrar la bandera.

>[!info]
>**A1Z26**
>Es un **cifrado de sustitución directa simple**, donde cada letra del alfabeto se reemplaza por su número en el alfabeto. Al decodificar, todos los números (del 1 al 26) deben estar separados por cualquier símbolo que no sea un dígito (guión, espacio).

## Referencias
[¿Cómo funciona el cifrado A1Z26?](https://reviews.tn/es/wiki/how-does-the-a1z26-cipher-work/)
[CyberChef](https://gchq.github.io/CyberChef/)