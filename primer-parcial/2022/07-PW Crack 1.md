# PW Crack 1

## Descripción
¿Puedes descifrar la contraseña para conseguir la bandera?
Descarga el comprobador de contraseñas [aquí](https://artifacts.picoctf.net/c/11/level1.py) y necesitarás también la [bandera](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) encriptada en el mismo directorio.

## Pistas
- Para ver el archivo en el webshell, haz: `$ nano nivel1.py`
- Para salir de `nano`, pulsa Ctrl y x y sigue las instrucciones en pantalla
- La función `str_xor` no necesita ingeniería inversa para este reto

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/11/level1.py
--2023-03-25 00:28:46--  https://artifacts.picoctf.net/c/11/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                            100%[=====================================================================================================================>]     876  --.-KB/s    in 0s      

2023-03-25 00:28:46 (455 MB/s) - 'level1.py' saved [876/876]

markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
--2023-03-25 00:29:05--  https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.74, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                                  100%[=====================================================================================================================>]      30  --.-KB/s    in 0s      

2023-03-25 00:29:05 (29.7 MB/s) - 'level1.flag.txt.enc' saved [30/30]

markofpride-picoctf@webshell:~$ ls
README.txt  code.py  codebook.txt  convertme.py  level1.flag.txt.enc  level1.py  runme.py
markofpride-picoctf@webshell:~$ cat level1.py 
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


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "1e1a"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()
markofpride-picoctf@webshell:~$ python3 level1.py 
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}
```

## Bandera
picoCTF{545h_r1ng1ng_fa343060}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| ls | Listar el contenido del directorio |
| python3 | Ejecuta código en lenguaje de programación python |

La solución está en la comparación de la función "level_1_pw_check"

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[ls(1) - Linux man page](https://linux.die.net/man/1/ls)
[PYTHON](https://www.commandlinux.com/man-page/man1/python3.1.html)