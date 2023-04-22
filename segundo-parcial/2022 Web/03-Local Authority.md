# Local Authority

## Descripción
¿Puedes conseguir la bandera?
Visite este [sitio web](http://saturn.picoctf.net:64710/) y vea lo que puede descubrir.

## Pistas
- ¿Cómo se comprueba la contraseña en este sitio web?

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:64710/login.php                                                   
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="style.css">
    <title>Login Page</title>
  </head>
  <body>
    <script src="secure.js"></script>
    
    <p id='msg'></p>
    
    <form hidden action="admin.php" method="post" id="hiddenAdminForm">
      <input type="text" name="hash" required id="adminFormHash">
    </form>
    
    <script type="text/javascript">
      function filter(string) {
        filterPassed = true;
        for (let i =0; i < string.length; i++){
          cc = string.charCodeAt(i);
          
          if ( (cc >= 48 && cc <= 57) ||
               (cc >= 65 && cc <= 90) ||
               (cc >= 97 && cc <= 122) )
          {
            filterPassed = true;     
          }
          else
          {
            return false;
          }
        }
        
        return true;
      }
    
      window.username = "";
      window.password = "";
      
      usernameFilterPassed = filter(window.username);
      passwordFilterPassed = filter(window.password);
      
      if ( usernameFilterPassed && passwordFilterPassed ) {
      
        loggedIn = checkPassword(window.username, window.password);
        
        if(loggedIn)
        {
          document.getElementById('msg').innerHTML = "Log In Successful";
          document.getElementById('adminFormHash').value = "2196812e91c29df34f5e217cfd639881";
          document.getElementById('hiddenAdminForm').submit();
        }
        else
        {
          document.getElementById('msg').innerHTML = "Log In Failed";
        }
      }
      else {
        document.getElementById('msg').innerHTML = "Illegal character in username or password."
      }
    </script>
    
  </body>
</html>
                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ curl http://saturn.picoctf.net:64710/secure.js



function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}

```

## Bandera
picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}

## Notas adicionales
En la función `checkPassword` se encuentra la condición que nos dará acceso como administrador solo debemos usar el usuario 'admin' y la contraseña 'strongPassword098765'

| Comando | Descripción |
|--------|--------|
| curl | Es una herramienta de línea de comandos de Linux que sirve para transferir datos hacia o desde un servidor con URL, utilizando cualquiera de los protocolos soportados |

## Referencias
[Cómo usar el comando curl de Linux](https://www.hostgator.mx/blog/comando-curl-linux/)