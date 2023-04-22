# Includes

## Descripción
¿Puedes conseguir la bandera?
Visite este [sitio web](http://saturn.picoctf.net:63115/) y vea lo que puede descubrir.

## Pistas
- ¿Hay más código del que muestra inicialmente el inspector?

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:63115/                          
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="style.css">
    <title>On Includes</title>
  </head>
  <body>
    <script src="script.js"></script>
  
    <h1>On Includes</h1>
    <p>Many programming languages and other computer files have a directive, 
       often called include (sometimes copy or import), that causes the 
       contents of a second file to be inserted into the original file. These 
       included files are called copybooks or header files. They are often used
       to define the physical layout of program data, pieces of procedural code
       and/or forward declarations while promoting encapsulation and the reuse
       of code.</p>
    <br>
    <p> Source: Wikipedia on Include directive </p>
    <button type="button" onclick="greetings();">Say hello</button>
  </body>
</html>
                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:63115/style.css
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */
                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:63115/script.js



function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_6edef411}

```

## Bandera
picoCTF{1nclu51v17y_1of2_f7w_2of2_6edef411}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| curl | Es una herramienta de línea de comandos de Linux que sirve para transferir datos hacia o desde un servidor con URL, utilizando cualquiera de los protocolos soportados |

## Referencias
[Cómo usar el comando curl de Linux](https://www.hostgator.mx/blog/comando-curl-linux/)