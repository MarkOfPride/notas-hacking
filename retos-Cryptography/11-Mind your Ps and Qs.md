# Mind your Ps and Qs

## Descripción
En RSA, un valor `e` pequeño puede ser problemático, pero ¿qué pasa con `N`? ¿Se puede descifrar? [valores](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)

## Pistas
- Los bits son caros, he utilizado sólo un poco más de 100 para ahorrar dinero

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/cryptography/MindyourPsandQs]
└─$ wget https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values               
--2023-04-30 21:44:33--  https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 206 [application/octet-stream]
Saving to: ‘values’

values                      100%[===========================================>]     206  --.-KB/s    in 0s      

2023-04-30 21:44:34 (134 MB/s) - ‘values’ saved [206/206]

                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/MindyourPsandQs]
└─$ cat values    
Decrypt my super sick RSA:
c: 964354128913912393938480857590969826308054462950561875638492039363373779803642185
n: 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
e: 65537                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/MindyourPsandQs]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> e = 65537
>>> p = 2434792384523484381583634042478415057961
>>> q = 650809615742055581459820253356987396346063
>>> n = p * q
>>> n
1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> tn = (p-1)*(q-1)
>>> d = inverse(e, tn)
>>> m = pow(c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639684640304028661985917
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_73918962}'
>>> exit()
```

## Bandera
picoCTF{sma11_N_n0_g0od_73918962}

## Notas adicionales
Utilizar un valor de `n` muy pequeño es muy problematico, ya que podemos utilizar herramientas computacionales (factordb.com en este caso concreto) para factorizar su valor y encontrar los valores de `p` y `q`.

## Referencias
[RSA algorithm](https://simple.wikipedia.org/wiki/RSA_algorithm)
[factordb](http://www.factordb.com/index.php?query=1584586296183412107468474423529992275940096154074798537916936609523894209759157543)