# Inspect HTML

## Descripción
¿Puedes conseguir la bandera?
Visite este [sitio web](http://saturn.picoctf.net:49699/) y vea lo que puede descubrir.

## Pistas
- ¿Qué es el inspector web en los navegadores web?

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:49699/                
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>On Histiaeus</title>
  </head>
  <body>
    <h1>On Histiaeus</h1>
    <p>However, according to Herodotus, Histiaeus was unhappy having to stay in
       Susa, and made plans to return to his position as King of Miletus by 
       instigating a revolt in Ionia. In 499 BC, he shaved the head of his 
       most trusted slave, tattooed a message on his head, and then waited for 
       his hair to grow back. The slave was then sent to Aristagoras, who was 
       instructed to shave the slaves head again and read the message, which 
       told him to revolt against the Persians.</p>
    <br>
    <p> Source: Wikipedia on Histiaeus </p>
        <!--picoCTF{1n5p3t0r_0f_h7ml_1fd8425b}-->
  </body>
</html>

```

## Bandera
picoCTF{1n5p3t0r_0f_h7ml_1fd8425b}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| curl | Es una herramienta de línea de comandos de Linux que sirve para transferir datos hacia o desde un servidor con URL, utilizando cualquiera de los protocolos soportados |

## Referencias
[Cómo usar el comando curl de Linux](https://www.hostgator.mx/blog/comando-curl-linux/)