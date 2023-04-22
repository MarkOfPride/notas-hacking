# waves over lambda

## Descripción
Hicimos muchas sustituciones para encriptar esto. ¿Puedes desencriptarlo? Conecta con `nc jupiter.challenges.picoctf.org 13758`

## Pistas
- La bandera no tiene el formato habitual

## Solución
```bash
markofpride-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 13758 
'-------------------------------------------------------------------------------
dopuhnqi cjhj vi yokh wgnu - whjmkjpdy_vi_d_orjh_gnlten_eprqwhqnyk
-------------------------------------------------------------------------------
tjqxjjp ki qcjhj xni, ni v cnrj nghjney inve ioljxcjhj, qcj tope ow qcj ijn. tjiveji cogevpu okh cjnhqi qoujqcjh qchokuc gopu zjhvoei ow ijznhnqvop, vq cne qcj jwwjdq ow lnfvpu ki qogjhnpq ow jndc oqcjhi ynhpinpe jrjp doprvdqvopi. qcj gnxyjhqcj tjiq ow oge wjggoxicne, tjdnkij ow cvi lnpy yjnhi npe lnpy rvhqkji, qcj opgy dkicvop op ejdf, npe xni gyvpu op qcj opgy hku. qcj nddokpqnpq cne thokucq okq nghjney n toa ow eolvpoji, npe xni qoyvpu nhdcvqjdqkhnggy xvqc qcj topji. lnhgox inq dhoii-gjuuje hvucq nwq, gjnpvpu nunvpiq qcj lvbbjp-lniq. cj cne ikpfjp dcjjfi, n yjggox dolzgjavop, n iqhnvucq tndf, np nidjqvd nizjdq, npe, xvqc cvi nhli ehozzje, qcj zngli ow cnpei okqxnhei, hjijltgje np veog. qcj evhjdqoh, inqviwvje qcj npdcoh cne uooe coge, lnej cvi xny nwq npe inq eoxp nlopuiq ki. xj jadcnpuje n wjx xohei gnbvgy. nwqjhxnhei qcjhj xni ivgjpdj op tonhe qcj yndcq. woh iolj hjniop oh oqcjh xj eve poq tjuvp qcnq unlj ow eolvpoji. xj wjgq ljevqnqvrj, npe wvq woh poqcvpu tkq zgndve iqnhvpu. qcj eny xni jpevpu vp n ijhjpvqy ow iqvgg npe jamkvivqj thvggvnpdj. qcj xnqjh icopj zndvwvdnggy; qcj ify, xvqcokq n izjdf, xni n tjpvup vlljpivqy ow kpiqnvpje gvucq; qcj rjhy lviq op qcj jiija lnhic xni gvfj n unkby npe hnevnpq wnthvd, ckpu whol qcj xooeje hviji vpgnpe, npe ehnzvpu qcj gox icohji vp evnzcnpoki wogei. opgy qcj ugool qo qcj xjiq, thooevpu orjh qcj kzzjh hjndcji, tjdnlj lohj iolthj jrjhy lvpkqj, ni vw npujhje ty qcj nzzhondc ow qcj ikp.'
```

**Bandera cifrada:** `dopuhnqi cjhj vi yokh wgnu - whjmkjpdy_vi_d_orjh_gnlten_eprqwhqnyk`

**Bandera descifrada:** `CONGRATS HERE IS YOUR FLAG - FREQUENCY_IS_C_OVER_LAMBDA_DNVTFRTAYU`

## Bandera
FREQUENCY_IS_C_OVER_LAMBDA_DNVTFRTAYU

## Notas adicionales
El conjunto de caracteres dado en el problema se decodificaron en **Cifrado por sustitución** usando la herramienta "Substitution cipher decoder" para encontrar la bandera. Esta página encontró que la llave para desencriptar el mensaje es `XZHCDKLRSEUMQAONTVJBGIFWYP`

>[!info]
>**Cifrado por sustitución**
>Es un método de cifrado por el que unidades de texto plano son sustituidas con texto cifrado siguiendo un sistema regular; las "unidades" pueden ser una sola letra (el caso más común), pares de letras, tríos de letras, mezclas de lo anterior, entre otros.

## Referencias
[Cifrado por sustitución](https://es.wikipedia.org/wiki/Cifrado_por_sustituci%C3%B3n)
[Substitution cipher decoder](https://planetcalc.com/8047/)