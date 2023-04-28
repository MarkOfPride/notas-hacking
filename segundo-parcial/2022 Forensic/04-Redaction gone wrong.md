# Redaction gone wrong

## Descripción
Ahora NO me ves.
Este [informe](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) contiene algunos datos críticos, algunos de los cuales se han redactado correctamente, mientras que otros no. ¿Puedes encontrar una clave importante que no se haya redactado correctamente?

## Pistas
- ¿Cómo puede estar seguro de la redacción?

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/forensic/Redactiongonewrong]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2023-04-23 16:06:45--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.38, 18.160.124.34, 18.160.124.119, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.38|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_for_ABC_Labs.pdf   100%[=================================================================>]  34.10K  --.-KB/s    in 0.1s    

2023-04-23 16:06:45 (341 KB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/Redactiongonewrong]
└─$ pdftotext Financial_Report_for_ABC_Labs.pdf
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/Redactiongonewrong]
└─$ ls
Financial_Report_for_ABC_Labs.pdf  Financial_Report_for_ABC_Labs.txt
                                                                                                                                              
┌──(kali㉿kali)-[~/picoctf/forensic/Redactiongonewrong]
└─$ cat Financial_Report_for_ABC_Labs.txt
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.

Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document.
```

## Bandera
picoCTF{C4n_Y0u_S33_m3_fully}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| pdftotext | Es una utilidad para la línea de comandos de código abierto que nos va a permitir convertir archivos PDF a archivos de texto simple |

## Referencias
[Pdftotext, convierte un PDF a texto desde la terminal](https://ubunlog.com/pdftotext-convierte-pdf-texto/#Instalar_pdftotext_en_Ubuntu)