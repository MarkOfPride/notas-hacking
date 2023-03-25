# PW Crack 2

## Descripción
¿Puedes descifrar la contraseña para conseguir la bandera?
Descarga el comprobador de contraseñas [aquí](https://artifacts.picoctf.net/c/13/level2.py) y necesitarás también la [bandera](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) encriptada en el mismo directorio.

## Pistas
- ¿Te resulta familiar esa codificación?
- La función `str_xor` no necesita ingeniería inversa para este reto.

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.py
--2023-03-25 00:33:53--  https://artifacts.picoctf.net/c/13/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                            100%[=====================================================================================================================>]     914  --.-KB/s    in 0s      

2023-03-25 00:33:53 (65.0 MB/s) - 'level2.py' saved [914/914]

markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
--2023-03-25 00:34:02--  https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.120, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                                  100%[=====================================================================================================================>]      31  --.-KB/s    in 0s      

2023-03-25 00:34:02 (9.48 MB/s) - 'level2.flag.txt.enc' saved [31/31]

markofpride-picoctf@webshell:~$ ls 
README.txt  code.py  codebook.txt  convertme.py  level1.flag.txt.enc  level1.py  level2.flag.txt.enc  level2.py  runme.py
markofpride-picoctf@webshell:~$ cat level2.py 
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
markofpride-picoctf@webshell:~$ python3 level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
```

## Bandera
picoCTF{tr45h_51ng1ng_489dea9a}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| ls | Listar el contenido del directorio |
| python3 | Ejecuta código en lenguaje de programación python |

La solución está en la comparación de la función "level_2_pw_check", sus caracteres están codificados en hexadecimal solo se tuvo que pasar cada valor hexadecimal a ASCII usando, en este caso, la herramienta "CyberChef"

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[ls(1) - Linux man page](https://linux.die.net/man/1/ls)
[PYTHON](https://www.commandlinux.com/man-page/man1/python3.1.html)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHgzNg)