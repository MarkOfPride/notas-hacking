# Based

## Descripción
Para llegar a ser realmente 1337, debes entender diferentes codificaciones de datos, como la hexadecimal o la binaria. ¿Puedes conseguir la bandera de este programa para demostrar que estás en camino de convertirte en 1337? Conéctate con nc jupiter.challenges.picoctf.org 15130.

## Pistas
- He oído que python puede convertir cosas
- Puede ser útil tener varias ventanas abiertas

## Solución
```bash
markofpride-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
container
Please give the 01100011 01101111 01101110 01110100 01100001 01101001 01101110 01100101 01110010 as a word.
...
you have 45 seconds.....

Input:
container
Please give me the  154 141 155 160 as a word.
Input:
lamp
Please give me the 636f6d7075746572 as a word.
Input:
computer
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_02167de8}
^C
```

## Bandera
picoCTF{learning_about_converting_values_02167de8}

## Notas adicionales
Para resolver el reto se utilizó la herramienta CyberChef para convertir las distintas cadenas en binario, octal y hexadecimal respectivamente, para más señas esta fue la receta de CyberChef:
```
From_Binary('Space',8)
From_Octal('Space')
From_Hex('Auto')
```

## Referencias
[CyberChef](https://gchq.github.io/CyberChef/)