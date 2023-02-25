# Bandit Level 15 → Level 16

## Objetivo
La contraseña para el siguiente nivel se puede recuperar enviando la contraseña del nivel actual al **puerto 30001 en localhost** utilizando encriptación SSL.

**Nota útil: ¿Obtiene "HEARTBEATING" y "Read R BLOCK"? Utilice -ign_eof y lea la sección "COMANDOS CONECTADOS" en la página de manual. Junto a 'R' y 'Q', el comando 'B' también funciona en esta versión de ese comando...**

## Datos de acceso al nivel
bandit.labs.overthewire.org
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 21 22:03:56 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 21 22:03:56 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 21 22:02:56 2023 GMT; NotAfter: Feb 21 22:03:56 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEF3vcjDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjIxMjIwMjU2WhcNMjMwMjIxMjIwMzU2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCg
1elREdWTbtCZNl7KNMjleNrcG71f9lZhjAfM4x+TDwlPpT+Q9O3V6J687fJdMH85
xfUwcZG0XFCeN1nxnmQadGF/ZHEt0laWmCQfo5LogzgGFcaZWC1a6XZ5ZKv7SRDt
tvPK/CTKwOJD5ZJVEXEk9R8YQ/VbKwZMDc43WD/HKypvBv7fZVbJkKYY75LOby86
7gux29Emhntj5pZyYagYbmonnAiw6447bGTC1d6jilGPhXMzckTI57WGeNdp4ppL
3pXSVDLOU2XJ8Um/L2VIgGTsUk5CwrtzVxyt6I5sKavUhsNGlzqvHI/McgbsnHi8
3LDg9k/Co8F21eZFooVlAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBz
lgp6XhMshglRxhxHRg1xHkVYSFSBaS5Adq5OIoE/oetyedTiO2B9MLmNZ9Juu/WK
/+WZFmNdzQ6Iw5ueBz/rmY+DvzTjjd4CPPqeilG5mngceR5nliM9mXkpQlmm3T1a
8JuBrDugrN9BP4IeBTER0pgQcQvsRATrv/SAVFVBhTSvOKFhoYNEdBzaqxclEjD6
bl3UkzNag/S3iLuv24xoQkMmlFC2afaswkG/cQ4p3BuapuZORjbohUOXS24QDl0z
A2RDFNizi42ZVJ8ZW1qbURZ4n/VbIAi7vRHldPKjC8hYAcdvUekB0schBlc1J06Z
phGCgzTVUzJu9yz8uKzO
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
    Session-ID: D8915D57384EC80B3C093F9E5808C3A26D6ECD29E14658E6F198C7507B06A44F
    Session-ID-ctx:
    Resumption PSK: B9671A44BAC9B112F4D5CF995FB1991D38E82562B5307366338ADBC9584525973BD533469F9F7D87D88755CC5909CF65
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - a5 3d 92 1f d1 78 36 48-bb a6 da 4d 19 13 ee a7   .=...x6H...M....
    0010 - b8 f6 d3 17 b0 34 09 3c-bd b4 f4 a8 23 6f b9 d7   .....4.<....#o..
    0020 - 52 66 fd 87 c9 b6 27 73-cb 33 8e 8e 76 86 80 93   Rf....'s.3..v...
    0030 - 62 12 d1 05 a0 48 f0 7b-db 0e d9 a5 f1 ce 57 d2   b....H.{......W.
    0040 - d6 0e e9 af d9 5f bb 6d-53 04 24 59 b3 a1 f5 19   ....._.mS.$Y....
    0050 - ea 6a 9c 18 7f f4 de de-2e c4 52 22 ce be 36 7f   .j........R"..6.
    0060 - 59 a8 0e 19 2e 3f f5 79-5f e8 66 1e d4 59 99 26   Y....?.y_.f..Y.&
    0070 - 66 70 a5 7e e9 a9 34 38-80 48 36 eb 63 17 d3 30   fp.~..48.H6.c..0
    0080 - e5 84 a1 9a 0c 2d 31 8e-c9 30 fc b8 21 3f fd ff   .....-1..0..!?..
    0090 - 78 8d be 12 0b 1f 5d f4-e7 d4 7e b8 6f c0 a7 b1   x.....]...~.o...
    00a0 - 43 f1 1c 30 b7 a9 56 1f-47 8f 69 04 e4 cc df 53   C..0..V.G.i....S
    00b0 - 12 94 97 74 d6 ba 3f 9d-08 44 d2 9c 92 77 39 77   ...t..?..D...w9w
    00c0 - 73 cc 5b 70 f7 df f8 db-26 bd b3 0a 6a bf 38 67   s.[p....&...j.8g

    Start Time: 1677107950
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
    Session-ID: 4B022CF153A5719911554E13FDB143D3CBCBE4D0652F1EEF0A20DDC91DCB7123
    Session-ID-ctx:
    Resumption PSK: B52CE7132BF4128BE81364A531BEA768050C6457AACAE36791CD7A2D8206D6F9A0488FC36D839CBD8F0F6A02A455C681
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - a5 3d 92 1f d1 78 36 48-bb a6 da 4d 19 13 ee a7   .=...x6H...M....
    0010 - 99 38 15 65 1a 69 c4 62-fc a6 e6 41 a5 75 4c 1b   .8.e.i.b...A.uL.
    0020 - 11 32 55 0f fe 3b b8 22-de 1d ff 55 65 09 03 f4   .2U..;."...Ue...
    0030 - 03 e4 f0 67 b9 06 5c 36-09 d9 5d fa 47 4d 92 7a   ...g..\6..].GM.z
    0040 - 0b d9 c0 ab f8 d3 67 f9-42 1f 41 cc 94 9f 49 2d   ......g.B.A...I-
    0050 - 73 eb 32 ad e7 7a 0e b3-01 35 d7 93 fe 7c 55 00   s.2..z...5...|U.
    0060 - 2b 2f f4 7d c9 84 0a 38-44 b1 c6 57 24 c3 06 99   +/.}...8D..W$...
    0070 - f4 82 0d 5a 78 f5 d3 3e-d2 36 54 47 9a 8a de 32   ...Zx..>.6TG...2
    0080 - fb 7e 0f 59 f6 44 2e 2d-21 34 62 b9 b8 94 b9 78   .~.Y.D.-!4b....x
    0090 - 39 86 52 4d f1 a0 ec e1-ae ab db 33 6f 4d ce e1   9.RM.......3oM..
    00a0 - 48 bd 42 bb b1 8a 02 e1-8c a6 36 38 56 55 2c 42   H.B.......68VU,B
    00b0 - 18 36 6e 46 fa a1 5b 64-db 0d ee b3 b1 26 23 9d   .6nF..[d.....&#.
    00c0 - 46 02 e3 89 a0 3e 95 65-8f fc a2 cd 99 e6 31 73   F....>.e......1s

    Start Time: 1677107950
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| openssl s_client | Implementa un cliente SSL/TLS genérico que se conecta a un host remoto utilizando SSL/TLS |
| -connect host:port | Especifica el host y el puerto opcional al que conectarse |

## Referencias
[s_client](https://www.openssl.org/docs/man1.0.2/man1/openssl-s_client.html)