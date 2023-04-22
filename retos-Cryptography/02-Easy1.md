# Easy1

## Descripción
El one time pad puede ser criptográficamente seguro, pero no cuando conoces la clave. ¿Puedes resolverlo? Te hemos dado la bandera encriptada, la clave y una tabla para ayudar a `UFJKXQZQUNB` con la clave de `SOLVECRYPTO`.
¿Puedes usar esta [tabla](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) para resolverlo?

## Pistas
- Envíe su respuesta en nuestro formato de bandera. Por ejemplo, si su respuesta es "hello", deberá enviar "picoCTF{HELLO}" como bandera.
- Por favor, utilice mayúsculas para el mensaje.

## Solución
**Mensaje cifrado:** `UFJKXQZQUNB`
**Llave de cifrado:** `SOLVECRYPTO`

**Bandera encontrada:** `CRYPTOISFUN`

## Bandera
PICOCTF{CRYPTOISFUN}

## Notas adicionales
El conjunto de caracteres dado en el problema se decodificaron en **Cifrado de Vigenère** usando la herramienta "CyberChef" y la llave de cifrado para encontrar la bandera.

>[!info]
>**Cifrado de Vigenère**
>Es un cifrado basado en diferentes series de caracteres o letras del cifrado César formando estos caracteres una tabla, llamada tabla de Vigenère, que se usa como clave. El cifrado de Vigenère es un cifrado por sustitución simple polialfabético.

## Referencias
[Cifrado de Vigenère](https://es.wikipedia.org/wiki/Cifrado_de_Vigen%C3%A8re)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkIg)