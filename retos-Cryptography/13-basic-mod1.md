# basic-mod1

## Descripción
Encontramos este extraño mensaje circulando por los servidores, creemos que tenemos un esquema de descifrado que funciona.
Descargue el mensaje [aquí](https://artifacts.picoctf.net/c/128/message.txt).
Tome cada número mod 37 y relaciónelo con el siguiente conjunto de caracteres: 0-25 es el alfabeto (mayúsculas), 26-35 son los dígitos decimales, y 36 es un guión bajo. Envuelva su mensaje descifrado en el formato de bandera picoCTF (ejemplo, picoCTF{mensaje_descifrado})

## Pistas
- ¿Sabes lo que significa `mod 37`?
- `mod 37` significa módulo 37. Da el resto de un número después de ser dividido por 37.

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/cryptography/basic-mod1]
└─$ wget https://artifacts.picoctf.net/c/128/message.txt                                   
--2023-04-30 22:18:28--  https://artifacts.picoctf.net/c/128/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.34, 18.160.124.108, 18.160.124.38, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.34|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 84 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                 100%[===========================================>]      84  --.-KB/s    in 0s      

2023-04-30 22:18:29 (46.7 MB/s) - ‘message.txt’ saved [84/84]

                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/basic-mod1]
└─$ cat message.txt 
165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138                                                                                                                 
┌──(kali㉿kali)-[~/picoctf/cryptography/basic-mod1]
└─$ nano exp.py
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/basic-mod1]
└─$ cat exp.py    
data = open('message.txt').read().split()

flag = ''

for n in data:
        c = int(n) % 37
        if c >= 0 and c <= 25:
                s = chr(c + 65)
        elif c >= 26 and c <= 35:
                s = chr(c + 22)
        else:
                s = '_'
        flag += s

print(f"picoCTF{{{flag}}}")
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/basic-mod1]
└─$ python3 exp.py
picoCTF{R0UND_N_R0UND_B6B25531}
```

## Bandera
picoCTF{R0UND_N_R0UND_B6B25531}

## Notas adicionales
Los scripts de python son MUY utiles.

## Referencias