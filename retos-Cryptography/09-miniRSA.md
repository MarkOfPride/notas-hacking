# miniRSA

## Descripción
Descifremos este: ¿[texto cifrado](https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext)? Algo parece un poco pequeño.

## Pistas
- [Tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem)) RSA
- ¿Cómo podría afectar a la seguridad de esta clave de 2048 bits tener una `e` demasiado pequeña?
- Asegúrate de no perder precisión, los números son bastante grandes (además del valor `e`)

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ cat ciphertext

N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125 
                                                                                                                                                        
┌──(kali㉿kali)-[~]
└─$ python3                                    
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from gmpy2 import *
>>> gmpy2.get_context().precision=2048
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125
>>> r, t = iroot(c, e)
>>> t
True
>>> r
mpz(13016382529449106065894479374027604750406953699090365388202874238148389207291005)
>>> long_to_bytes(r)
b'picoCTF{n33d_a_lArg3r_e_606ce004}'
>>> exit()
```

## Bandera
picoCTF{n33d_a_lArg3r_e_606ce004}

## Notas adicionales
En el reto anterior se colocaron las formulas necesarias para resolver este problema. ¡Echale un vistazo! [[08-rsa-pop-quiz]].
Este articulo [Twenty Years of Attacks on the RSA Cryptosystem](https://crypto.stanford.edu/~dabo/pubs/papers/RSA-survey.pdf) explica porque un exponenete muy pequeño logra hecer que la n sea innecesaria para desencriptar el mensaje. 

## Referencias
[RSA algorithm](https://simple.wikipedia.org/wiki/RSA_algorithm)
