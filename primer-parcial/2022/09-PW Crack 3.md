# PW Crack 3

## Descripción
¿Puedes descifrar la contraseña para obtener la bandera?
Descarga el comprobador de contraseñas [aquí](https://artifacts.picoctf.net/c/17/level3.py) y también necesitarás la [bandera](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) encriptada y el [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) en el mismo directorio.
Hay 7 contraseñas potenciales, siendo 1 la correcta. Puedes encontrarlas examinando el script del comprobador de contraseñas.

## Pistas
- Para ver el archivo level3.hash.bin en el webshell, haga: `$ bvi level3.hash.bin`
- Para salir de `bvi` escribe `:q` y pulsa intro
- La función `str_xor` no necesita ingeniería inversa para este reto

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.py
--2023-03-25 01:13:57--  https://artifacts.picoctf.net/c/17/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                            100%[=====================================================================================================================>]   1.31K  --.-KB/s    in 0s      

2023-03-25 01:13:57 (66.9 MB/s) - 'level3.py' saved [1337/1337]

markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
--2023-03-25 01:14:06--  https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.120, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                                  100%[=====================================================================================================================>]      31  --.-KB/s    in 0s      

2023-03-25 01:14:06 (33.5 MB/s) - 'level3.flag.txt.enc' saved [31/31]

markofpride-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.hash.bin
--2023-03-25 01:14:16--  https://artifacts.picoctf.net/c/17/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.42, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                                      100%[=====================================================================================================================>]      16  --.-KB/s    in 0s      

2023-03-25 01:14:16 (1.13 MB/s) - 'level3.hash.bin' saved [16/16]

markofpride-picoctf@webshell:~$ ls
README.txt  code.py  codebook.txt  convertme.py  level1.flag.txt.enc  level1.py  level2.flag.txt.enc  level2.py  level3.flag.txt.enc  level3.hash.bin  level3.py  runme.py
markofpride-picoctf@webshell:~$ cat level3.py
import hashlib

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

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

markofpride-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: f09e
That password is incorrect
markofpride-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: 4dcf
That password is incorrect
markofpride-picoctf@webshell:~$ python3 level3.py 
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
```

## Bandera
picoCTF{m45h_fl1ng1ng_cd6ed2eb}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| ls | Listar el contenido del directorio |
| python3 | Ejecuta código en lenguaje de programación python |

La solución se encuentra al probar una a una las siete contraseñas posibles en el comprobador de contraseñas, las opciónes se encuentran dentro del arreglo "pos_pw_list"

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[ls(1) - Linux man page](https://linux.die.net/man/1/ls)
[PYTHON](https://www.commandlinux.com/man-page/man1/python3.1.html)