# SRA

## Descripción
Hace poco conocí el criptosistema de clave pública SRA... o espera, ¿se suponía que era RSA? Hmmm, probablemente debería comprobarlo...
Conéctese al programa en nuestro servidor: `nc saturn.picoctf.net 52177`
Descárgate el programa: [chal.py](https://artifacts.picoctf.net/c/295/chal.py)

## Pistas
- (None)

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/cryptography/SRA]
└─$ cat chal.py  
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/SRA]
└─$ cat exp.py 
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

def sub_lists (l):
        comb = []
        for i in range(1,len(l)+1):
                comb += [list(j) for j in combinations(l, i)]
        return comb

def divisors(phi):
        print("Give me the divisors of ", phi-1)
        return(eval(input()))

r = remote('saturn.picoctf.net', 59697)
r.recvuntil("anger = ")
ciphertext=int(r.recvline())
r.recvuntil("envy = ")
d=int(r.recvline())
print("cipher = ",ciphertext)
print("d = ",d)
print(r.recvuntil("vainglory?"))
r.recvline()
factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()

for l in combos:
        product = 1
        for k in l:
                product = product * k
        if product.bit_length()==128 and primefac.isprime(product+1):
                primes.add(product+1)
print(primes)
primelist = list(primes)

for p in primelist:
        for q in primelist:
                n=p*q
                plain = pow(ciphertext,d,n)
                try:
                        plaintext = long_to_bytes(plain)
                        print(plaintext.decode())
                        r.sendline(plaintext.decode())
                        print(r.recvline())
                        print(r.recvline())
                        print(r.recvline())
                except:
                        continue
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/SRA]
└─$ python3 exp.py
[+] Opening connection to saturn.picoctf.net on port 59697: Done
/home/kali/picoctf/cryptography/SRA/exp.py:17: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger = ")
/home/kali/picoctf/cryptography/SRA/exp.py:19: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy = ")
cipher =  25528224855920448484620743015761812560996580269307749014215091558267706426816
d =  1505228773110065599612813739915154386804919170189305173296042873955194553713
/home/kali/picoctf/cryptography/SRA/exp.py:23: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  98648178103314369201824974072819473048033987656696493142302761830401585466688880
[2, 2, 2, 2, 3, 3, 3, 3, 3, 3, 5, 7, 109, 15739, 1467299, 1223251649, 229577295354638444042171, 341827118137900940136615899947]
{197037743061127616172776678706711867793, 315984430828473064283755315227089886391, 312064918982580098068352053623578922661, 318239715003349906639765891181014522633}
txC0y5d4tqEIsdTy
/home/kali/picoctf/cryptography/SRA/exp.py:45: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> txC0y5d4tqEIsdTy\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}\r\n'
txC0y5d4tqEIsdTy
[*] Closed connection to saturn.picoctf.net port 59697
```

## Bandera
picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}

## Notas adicionales

## Referencias
[Prime Factors Decomposition](https://www.dcode.fr/prime-factors-decomposition)