# Vigenere

## Descripción
¿Puedes desencriptar este mensaje?
Descifra este [mensaje](https://artifacts.picoctf.net/c/160/cipher.txt) usando esta clave "CYLAB".

## Pistas
- https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher

## Solución
**Mensaje codificado:** rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}
**Llave:** CYLAB

**Mensaje decodificado:** picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}

>[!solution]
>La bandera fue obtenida usando el Vigenère Decoder que ofrece la herramienta "CyberChef", solo se le pasó el texto codificado y la llave proporcionada.

## Bandera
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}

## Notas adicionales
>[!info]
>**Cifrado de Vigenère**
>Es un método de cifrado de texto alfabético en el que cada letra del texto plano se codifica con un cifrado César diferente, cuyo incremento viene determinado por la letra correspondiente de otro texto, la clave.

## Referencias
[Vigenère cipher](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfMjk1MWM4OWZ9)