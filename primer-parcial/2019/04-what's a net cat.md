# what's a net cat?

## Descripción
Usar netcat (nc) va a ser bastante importante. Puede conectarse a jupiter.challenges.picoctf.org en el puerto 25103 para obtener la bandera?

## Pistas
- nc [tutorial](https://linux.die.net/man/1/nc)

## Solución
```bash
markofpride-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 25103
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_d0c64587}
^C
```

## Bandera
picoCTF{nEtCat_Mast3ry_d0c64587}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| nc | La utilidad nc (o netcat) se utiliza para casi cualquier cosa bajo el sol que implique TCP o UDP |

## Referencias
[nc(1) - Linux man page](https://linux.die.net/man/1/nc)