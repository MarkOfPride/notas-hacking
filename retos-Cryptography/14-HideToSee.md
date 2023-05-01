# HideToSee

## Descripción
¿Qué tal un poco de escondite?
Mira esta [imagen](https://artifacts.picoctf.net/c/240/atbash.jpg).

## Pistas
- Descarga la imagen e intenta extraerla

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/cryptography/HideToSee]
└─$ wget https://artifacts.picoctf.net/c/240/atbash.jpg 
--2023-04-30 22:32:36--  https://artifacts.picoctf.net/c/240/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.108, 18.160.124.34, 18.160.124.38, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.108|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51508 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                  100%[===========================================>]  50.30K  --.-KB/s    in 0.03s   

2023-04-30 22:32:37 (1.52 MB/s) - ‘atbash.jpg’ saved [51508/51508]

                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/HideToSee]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/HideToSee]
└─$ ls
atbash.jpg  encrypted.txt
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/HideToSee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_xz00558y}
```

## Bandera
picoCTF{atbash_crack_ca00558b}

## Notas adicionales
Como el nombre del archivo lo insinuaba, la bandera resultante está cifrada con un método muy común de cifrado llamado `Atbash` el cual fue descifrado usando la herramienta "CyberChef".

| Comando | Descripción |
|--------|--------|
| steghide | Extrae bits de un archivo de datos en algunos de los bits menos significativos de otro archivo |

## Referencias
[steghide](https://www.kali.org/tools/steghide/)
[Atbash](https://es.wikipedia.org/wiki/Atbash)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,121/disabled)Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfeHowMDU1OHl9)