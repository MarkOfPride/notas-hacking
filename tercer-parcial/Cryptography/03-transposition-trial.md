# transposition-trial

## Descripción
Nuestros datos se corrompieron en el camino. Por suerte, nada fue reemplazado, ¡pero cada bloque de 3 fue revuelto! La primera palabra parece tener tres letras, tal vez puedas usarla para recuperar el resto del mensaje.
Descargue [aquí](https://artifacts.picoctf.net/c/191/message.txt) el mensaje dañado.

## Pistas
- Divida el mensaje en bloques de 3 y vea cómo se codifica el primer bloque

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/cryptography/transposition-trial]
└─$ cat message.txt
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/transposition-trial]
└─$ cat TranspositionTrial.java
public class TranspositionTrial {
        public static void main(String[] args) {
                String banderaC = "heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4";
                StringBuilder banderaD = new StringBuilder();
                for (int i = 0; i < banderaC.length(); i++) {
                        if(i % 3 == 0){
                                banderaD.append(banderaC.charAt(i + 2)).append(banderaC.charAt(i));
                        } else if (i % 3 == 2) {
                                //Nada pa
                        } else {
                                banderaD.append(banderaC.charAt(i));
                        }
                }
                System.out.println(banderaD);
        }
}
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/cryptography/transposition-trial]
└─$ java TranspositionTrial
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A}
```

## Bandera
picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A}

## Notas adicionales
>[!solution]
>El texto que contiene la bandera tiene los caracteres mezclados, al separar en bloques de tres como sugiere la pista, denotamos que el primer caracter de cada grupo se colocó al final.

## Referencias