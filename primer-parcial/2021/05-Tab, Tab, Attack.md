# Tab, Tab, Attack

## Descripción
El uso de tabcomplete en el Terminal le añadirá años a su vida, especialmente cuando se trate de largas estructuras de directorios y nombres de archivos: [Addadshashanammu.zip](https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip)

## Pistas
- Después de `descomprimir`, este problema se soluciona con 11 pulsaciones de botón...(la mayoría Tab)...

## Solución
```bash
markofpride-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
--2023-03-24 05:24:37--  https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                                 100%[=====================================================================================================================>]   4.41K  --.-KB/s    in 0s      

2023-03-24 05:24:37 (1.52 GB/s) - 'Addadshashanammu.zip' saved [4520/4520]

markofpride-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
markofpride-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
markofpride-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ cat fang-of-haynekhtnamet | strings | grep pico           
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| wget | Es una utilidad gratuita para la descarga no interactiva de archivos de la Web |
| unzip | Listará, probará o extraerá ficheros de un archivo ZIP, comúnmente encontrado en sistemas MS-DOS |
| cat | Concatenar archivos e imprimir en la salida estándar |
| strings | Imprimir las secuencias de caracteres imprimibles en ficheros |
| grep | Busca PATRONES en cada ARCHIVO |

## Referencias
[wget(1) - Linux man page](https://linux.die.net/man/1/wget)
[unzip(1) - Linux man page](https://linux.die.net/man/1/unzip)
[cat(1) - Linux man page](https://linux.die.net/man/1/cat)
[strings(1) — Linux manual page](https://man7.org/linux/man-pages/man1/strings.1.html)
[grep(1) — Linux manual page](https://man7.org/linux/man-pages/man1/grep.1.html)