# Mr-Worldwide

## Descripción
Un músico nos dejó un [mensaje](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). ¿Qué significa?

## Pistas
- (None)

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/cryptography/Mr-Worldwide]
└─$ cat message.txt
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)} 
```

>[!solution]
>Para solucionar este reto, es bastante claro que los datos entre parentesis son coordenadas, al buscarlas en la herramienta "Google maps", esto nos lleva a diferentes localizaciones la primera letra del nombre del lugar forma la bandera. MUY rebuscado.

## Bandera
picoCTF{KODIAK_ALASKA}

## Notas adicionales

## Referencias
[Google maps](https://www.google.com.mx/maps/@28.4240545,-91.8915445,3z)