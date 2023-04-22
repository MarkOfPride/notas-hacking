# Tapping

## Descripción
Hay un golpeteo en los cables. ¿Qué dice? `nc jupiter.challenges.picoctf.org 9422`

## Pistas
- ¿Qué tipo de codificación utiliza guiones y puntos?
- La bandera tiene el formato PICOCTF{}

## Solución
```bash
markofpride-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 9422
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }
```

**Bandera cifrada:** `.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }`

**Bandera descifrada:** `PICOCTF{M0RS3C0D31SFUN2683824610}`

## Bandera
PICOCTF{M0RS3C0D31SFUN2683824610}

## Notas adicionales
El conjunto de caracteres dado en el problema se decodificaron en **código morse** usando la herramienta "CyberChef" para encontrar la bandera.

>[!info]
>**Código morse**
>Es un sistema de representación de letras y números mediante señales emitidas de forma intermitente (guiones y puntos).

## Referencias
[Código morse](https://es.wikipedia.org/wiki/C%C3%B3digo_morse)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4uLS0tIC0uLi4uIC0tLS4uIC4uLi0tIC0tLS4uIC4uLS0tIC4uLi4tIC0uLi4uIC4tLS0tIC0tLS0tIH0)