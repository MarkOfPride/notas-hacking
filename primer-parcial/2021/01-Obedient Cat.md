# Obedient Cat

## Descripción
Este archivo tiene una bandera a la vista (también conocida como "in-the-clear").
[Download flag](https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag).

## Pistas
- Cualquier sugerencia sobre cómo introducir un comando en el Terminal (como la siguiente), empezará con un '$'... todo lo que venga después del signo de dólar será tecleado (o copiado y pegado) en tu Terminal.
- Para obtener el archivo accesible en su shell, introduzca lo siguiente en el prompt de Terminal: `$ wget https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag`
- $ man cat

## Solución
```bash
markofpride-picoctf@webshell:~$ curl https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag
picoCTF{s4n1ty_v3r1f13d_1a94e0f9}
```

## Bandera
picoCTF{s4n1ty_v3r1f13d_1a94e0f9}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| curl | Es una herramienta para transferir datos desde o hacia un servidor, utilizando uno de los protocolos admitidos |

## Referencias
[curl(1) - Linux man page](https://linux.die.net/man/1/curl)