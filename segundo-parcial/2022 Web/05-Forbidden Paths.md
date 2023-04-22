# Forbidden Paths

## Descripción
¿Puedes conseguir la bandera?
Aquí está la [página web](http://saturn.picoctf.net:52021/)
Sabemos que los archivos del sitio web viven en /usr/share/nginx/html/ y la bandera está en /flag.txt pero el sitio web está filtrando las rutas absolutas de los archivos. ¿Puedes pasar el filtro para leer la bandera?

## Pistas
- (None)

## Solución
Se realiza un ataque de path traversal para lograr acceder a la bandera, basicamente se escribe el tipico ../ con el texto flag.txt hasta que esta se muestre.
`../../../../flag.txt`

## Bandera
picoCTF{7h3_p47h_70_5ucc355_e5fe3d4d}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| Path Traversal | Un ataque path traversal tiene como objetivo acceder a archivos y directorios que se almacenan fuera de la carpeta raíz de la web |

## Referencias
[Path Traversal](https://owasp.org/www-community/attacks/Path_Traversal)