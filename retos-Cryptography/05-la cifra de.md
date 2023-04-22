# la cifra de

## Descripción
Encontré esta cifra en un libro viejo. ¿Puedes averiguar qué dice? Conecta con `nc jupiter.challenges.picoctf.org 58295`

## Pistas
- Existen herramientas que facilitan esta tarea
- Quizás mirar la historia ayude

## Solución
```bash
markofpride-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 58295 
'Encrypted message:
Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo 

Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3xf966878l}

Tnj qixxe wkqw-duhfmkseej ipsiwtpznzn uk l puqjarusahjeii htpnjc hubpvkw, hay rldk fcoaso 1467 be Qpot Gltzndtg Fwbkwei.

Zmp Volpnèxj Nivmpr ox ehkwpfuwp surptorps ifwlki ehk Fwbkwei Jndc uw Llhjcto Htpnjc.

It 1508, Ozhgsyey Ycizmpmozd itapnzjo tnj do-ifwlki eahzwa xjntg (f xazwtx uk dhokeej fwpnfmezx) ehgy hoaqo lgypr hj l cxneiifw curaotjyt uk ehk Atgksèce Inahkw.

Merqlsu’x deityd htzkrje avupaxjo it 1555 fd a itytosfaznzn uk ehk ktryy. Ehk qzwkw saraps uk ehk fwpnfmezx lrk szw ymtfzjo rklflgwwy, hze tnj llvmlbkyd ati ehk nydkc wezypry fce sniej gj mkfys uk l mtjxotnn kkd ahxfde, cmtcn hln hj oilkprkse woys eghs cuwceyuznjjyt.'
```

**Bandera cifrada:** `pohzCZK{m311a50_0x_a1rn3x3_h1ah3xf966878l}`

**Bandera descifrada:** `picoCTF{b311a50_0r_v1gn3r3_c1ph3ra966878a}`

## Bandera
picoCTF{b311a50_0r_v1gn3r3_c1ph3ra966878a}

## Notas adicionales
El conjunto de caracteres dado en el problema se decodificaron en **Cifrado de Vigenère** usando la herramienta "CyberChef", pero en este caso no nos proporcionan la llave de cifrado, por lo que se usó otra herramienta llamada "Vigenere Cipher", esta página nos dió varias opciones como posible llave entre ellas resaltan: "FLGG", "LAGF" y "FLFG" lo que me hace pensar que la llave usada es "FLAG" al introducirla en "CyberChef" resultó ser la correcta.

## Referencias
[Cifrado de Vigenère](https://es.wikipedia.org/wiki/Cifrado_de_Vigen%C3%A8re)
[Vigenere Cipher](https://www.dcode.fr/vigenere-cipher)
[CyberChef](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('FLAG')&input=TmUgaXkgbnl0a3dwc3pueWcgbnRoIGl0IG10c3p0Y3kgdmp6cHJqIHpmemp5IHJraHBpYmogbnJraXR0IGx0YyB0bm55Z3kgeXNlZSBpdGQgdHRlIGN4amx0awoKSWZyb3NyIHRuaiBub2F3ZGUgdWsgc2l5eXpyZSwgeXNlIEJucmV0w6h3cCBDb3VzZXggbWxzIGhqcG4geGp0bmJqeXRraSB4YXRkIGVpc2pkCgpJeiBibHMgbGZ3c2txaiBhenljaWh6ZWVqIHl6IEJyZnRzayBpcCBWb2xwbsOoeGogbHMgb3kgaGF5IHRjaW1ueWFycWogZGt4bnJvZ3BkIG9zIDE1NTMgbXkgTW56dmdzIE1henl0c3pmIE1lcnFsc3UgbnkgaG94IG1vdXAgV2EgaW5xcmcgaXBsLiBZbnIuIEdvdGdhdCBHbHR6bmR0ZyBHcGxyZmRvIAoKTHRjIHRuaiB0bXZxcG1rc2Vhem56biB1ayBlaG94IG5pdm1wciBnIHlsYnJqIHRzIGx0Y21raSBteSB5cXRkb3NyIHRuaiB3b2NqYyBoZ3FxIG9sIGZ5IG94aXRuZ3dqIGFydXNhaGplIGZ1dyBsbiBndWFheGp5dHJkIGNhdGl6bSB0enhia3cgemYgdnFsY2t4IGhpem0gY2V5dXBjeiB5eiB0bmogZnB2amMgaGdxcXBvaHpDWkt7bTMxMWE1MF8weF9hMXJuM3gzX2gxYWgzeGY5NjY4NzhsfQoKVG5qIHFpeHhlIHdrcXctZHVoZm1rc2VlaiBpcHNpd3Rwem56biB1ayBsIHB1cWphcnVzYWhqZWlpIGh0cG5qYyBodWJwdmt3LCBoYXkgcmxkayBmY29hc28gMTQ2NyBiZSBRcG90IEdsdHpuZHRnIEZ3Ymt3ZWkuCgpabXAgVm9scG7DqHhqIE5pdm1wciBveCBlaGt3cGZ1d3Agc3VycHRvcnBzIGlmd2xraSBlaGsgRndia3dlaSBKbmRjIHV3IExsaGpjdG8gSHRwbmpjLgoKSXQgMTUwOCwgT3poZ3N5ZXkgWWNpem1wbW96ZCBpdGFwbnpqbyB0bmogZG8taWZ3bGtpIGVhaHp3YSB4am50ZyAoZiB4YXp3dHggdWsgZGhva2VlaiBmd3BuZm1lengpIGVoZ3kgaG9hcW8gbGd5cHIgaGogbCBjeG5laWlmdyBjdXJhb3RqeXQgdWsgZWhrIEF0Z2tzw6hjZSBJbmFoa3cuCgpNZXJxbHN14oCZeCBkZWl0eWQgaHR6a3JqZSBhdnVwYXhqbyBpdCAxNTU1IGZkIGEgaXR5dG9zZmF6bnpuIHVrIGVoayBrdHJ5eS4gRWhrIHF6d2t3IHNhcmFwcyB1ayBlaGsgZndwbmZtZXp4IGxyayBzencgeW10ZnpqbyBya2xmbGd3d3ksIGh6ZSB0bmogbGx2bWxia3lkIGF0aSBlaGsgbnlka2Mgd2V6eXByeSBmY2Ugc25pZWogZ2ogbWtmeXMgdWsgbCBtdGp4b3RubiBra2QgYWh4ZmRlLCBjbXRjbiBobG4gaGogb2lsa3Bya3NlIHdveXMgZWdocyBjdXdjZXl1em5qanl0Lg)