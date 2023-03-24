# Magikarp Ground Mission

## Descripción
¿Sabes cómo moverte entre directorios y leer archivos en el shell? Inicia el contenedor, `ssh` a él, y luego `ls` una vez conectado para comenzar. Inicie sesión a través de `ssh` como `ctf-player` con la contraseña, `ee388b88`.
Los detalles adicionales estarán disponibles después de lanzar su instancia de desafío.

## Pistas
- Sería muy útil encontrar una hoja de trucos para bash.

## Solución
```bash
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~ 
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
3ca613a1}
ctf-player@pico-chall$ exit
logout
```

## Bandera
picoCTF{xxsh_0ut_0f_\\/\\/4t3r_3ca613a1}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| ls | Listar el contenido del directorio |
| cd | Cambia el directorio actual |
| cat | Concatenar archivos e imprimir en la salida estándar |

## Referencias
[ls(1) - Linux man page](https://linux.die.net/man/1/ls)
[cat(1) - Linux man page](https://linux.die.net/man/1/cat)