# Bandit Level 16 → Level 17

## Objetivo
Las credenciales para el siguiente nivel se pueden recuperar enviando la contraseña del nivel actual a un puerto en **localhost en el rango 31000 a 32000**. Primero averigua cuáles de estos puertos tienen un servidor escuchando en ellos. Luego averigua cuáles de ellos hablan SSL y cuáles no. Sólo hay 1 servidor que dará las siguientes credenciales, los demás simplemente te devolverán lo que le envíes.

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solución
```bash
bandit16@bandit:~$ nmap -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-02-25 01:14 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00011s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.07 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 24 22:59:05 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 24 22:59:05 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 24 22:58:05 2023 GMT; NotAfter: Feb 24 22:59:05 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEXaCVVzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjI0MjI1ODA1WhcNMjMwMjI0MjI1OTA1WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDP
cZ+PR+x7nAI6TVhZvc6x5//nXHJUZnIv2kf6x8SOY5al5BV8I5njUSVQef9fQNE2
JlBdoYNJ65jgzYWrVqPCObCqrPsHZHf8pMD/iElYUcD5u/qtNReuVPfeYefxCvBg
Cy0MltMiLGskDn3rDSwCRWNB2jr9+jQYa7rIGDyWCAq4WH/IsWtF6tan25Bqe6tp
LIMJhuAH56EjZ0biNJ3aOgsWHwqS1bBdMzURABvR+PZc0mikWaNjb2R0d8v0gJTf
qz0qkea6IstFSfwEu2FdslmDZ8PWlIwexw3erL+Ae0L2mFhdf3g1nkUARl8R0Bbe
L9/rtYsV7dF3KG7CFJbbAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBH
HpXhIirw6+X3VNmrtXw7HjpriGDA1UTjP2yfeu2YuLIm83iUpz3HuiiwsfJJX9HY
VeDQnJjgMekib2qbq99OHkz+4jFKpw0zR7wTa9K8fifkrQHW/KJOVg1fmJCyFl+j
LF06QYp5f8yA+I2ICGKuNSXd3NvYEVh0tWVXemx/oXqQLHUFBjWNcyBDfCnfZIfe
jhHPhGj/9DuJJWx1lBEOIFHrfOj2uge0R5YZvU0kEm3IQ6iabWM2JF8MHOWWYX8s
wXL4aeNo+K4lnz3wjqnRfSClTwTo9zvaaq+Ym8UxPx3w7SmAU3CXbLh/ukYR6xYp
YEsSAXuYvKkxrTvey2Ik
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: C4DAB64F0248DB7B3996C56CD3E4D5DE2101848D622B1CBDEFA13EC08ACC5A28
    Session-ID-ctx:
    Resumption PSK: 432B1CD08EB8FF9728D0904CA29E67A870F18CA4B86632F00733A0C1C5CBD24BC5F70E22D7D992858B9DD696CA418DC1
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 70 f2 f5 0a f4 da 59 2b-66 40 bc 3c 8d 67 67 76   p.....Y+f@.<.ggv
    0010 - f3 22 84 9e 94 e5 50 6d-03 ee 5e fb c0 be a7 a4   ."....Pm..^.....
    0020 - a4 14 a2 65 94 2d 92 26-4a da 54 6b 28 35 71 e0   ...e.-.&J.Tk(5q.
    0030 - 17 6c fa 90 b8 16 62 ce-00 b0 c5 44 28 e9 9c d5   .l....b....D(...
    0040 - 1f 73 71 53 65 53 4d e2-b1 10 4c 8f d1 b7 4a 9b   .sqSeSM...L...J.
    0050 - 4c fd a7 94 2b e2 0b 1f-28 a7 2e 1b 2b 13 bc de   L...+...(...+...
    0060 - bb 72 85 33 80 6d d4 44-63 15 4a 0d 5b 00 7a 86   .r.3.m.Dc.J.[.z.
    0070 - 6d 3d f9 9a a2 db 16 0c-b8 fc 9d 28 95 e8 5e ea   m=.........(..^.
    0080 - 23 fc a4 04 99 a9 cd ab-c7 32 54 ff b6 2f 8e 77   #........2T../.w
    0090 - b1 94 a0 eb 93 72 e4 c3-b6 5c 84 12 88 9d eb 00   .....r...\......
    00a0 - ff e6 2f 81 67 57 ec 5d-ea 6c 9e 0e af 4c ae cd   ../.gW.].l...L..
    00b0 - bc 34 21 34 b6 28 2e 53-b4 3f b6 8b c2 93 6c 23   .4!4.(.S.?....l#
    00c0 - 9a ca 34 52 98 28 13 fd-fc b1 cf 4d 1a d7 55 b5   ..4R.(.....M..U.

    Start Time: 1677287716
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 727AA7FCCF82F917454EA0F60A7302750E172CF726B0A918AFC4844A7040F73A
    Session-ID-ctx:
    Resumption PSK: 671305C7B4E374ADEC147095DB991CA331893ECE9046E266B6949463A4B8161DA40DD11A734C712E0006184FF4AFAE99
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 70 f2 f5 0a f4 da 59 2b-66 40 bc 3c 8d 67 67 76   p.....Y+f@.<.ggv
    0010 - 1f 00 97 76 8d 85 cb 1d-31 05 4b 9c 47 5c 0b 74   ...v....1.K.G\.t
    0020 - a2 74 bf e4 59 b0 2f e3-6b e3 4b b1 98 e9 3a 87   .t..Y./.k.K...:.
    0030 - ad 43 78 5a f8 4b 61 46-d4 2e 1d 1e 0b 2c 97 d1   .CxZ.KaF.....,..
    0040 - 8d 61 14 76 b2 54 01 8e-9c 04 3d fa bb 57 7f 7d   .a.v.T....=..W.}
    0050 - 0a d1 b4 5a 8b 64 ab 36-03 d8 9b d9 58 6b 6f 9d   ...Z.d.6....Xko.
    0060 - e2 02 98 e9 b0 60 86 7f-36 58 d1 66 4d 94 8f 5b   .....`..6X.fM..[
    0070 - d5 0d e5 ed 58 12 01 6e-08 f6 c7 55 2b 83 da f3   ....X..n...U+...
    0080 - 67 b3 93 f3 07 41 1f 36-0c a1 0d ff 1a b3 a6 35   g....A.6.......5
    0090 - 50 ee b4 65 e9 8d 97 64-c9 ad 5d c7 59 c8 e0 1a   P..e...d..].Y...
    00a0 - 31 af 92 96 76 38 30 df-56 17 ea e9 d9 82 82 87   1...v80.V.......
    00b0 - 85 89 f7 b3 48 4b 31 f7-40 2a b1 86 a8 16 3d 1e   ....HK1.@*....=.
    00c0 - be a2 d6 0a 25 86 5c 9a-20 bc 79 20 98 f5 d4 01   ....%.\. .y ....

    Start Time: 1677287716
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
```
```bash
C:\Users\Ricardo>ssh -i llave.txt bandit17@bandit.labs.overthewire.org -p 2220


bandit17@bandit:~$ cat /etc/bandit_pass/bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
bandit17@bandit:~$ exit
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| nmap | Permite escanear los puertos en busca de puertos abiertos |
| nmap -p | Se detalla el rango de puertos a escanear |
## Referencias
[Realiza escaneos de puertos con Nmap a cualquier servidor o sistema](https://www.redeszone.net/tutoriales/configuracion-puertos/nmap-escanear-puertos-comando)