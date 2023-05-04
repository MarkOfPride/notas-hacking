# vault-door-training

## Descripción
Tu misión es entrar en el laboratorio del Dr. Maligno y recuperar los planos de su Proyecto del Juicio Final. El laboratorio está protegido por una serie de puertas acorazadas cerradas con llave. Cada puerta está controlada por un ordenador y requiere una contraseña para abrirse. Desafortunadamente, nuestros agentes encubiertos no han podido obtener las contraseñas secretas de las puertas de las bóvedas, ¡pero uno de nuestros agentes junior obtuvo el código fuente del ordenador de cada bóveda! Tendrás que leer el código fuente de cada nivel para averiguar cuál es la contraseña de esa puerta de cámara acorazada. Como calentamiento, hemos creado una réplica de la cámara acorazada en nuestras instalaciones de entrenamiento. El código fuente de la bóveda de entrenamiento está aquí: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java)

## Pistas
- La contraseña se revela en el código fuente del programa

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/vault-door-training]
└─$ wget https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java
--2023-05-02 14:06:35--  https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 943 [application/octet-stream]
Saving to: ‘VaultDoorTraining.java’

VaultDoorTraining.java      100%[===========================================>]     943  --.-KB/s    in 0s      

2023-05-02 14:06:44 (24.6 MB/s) - ‘VaultDoorTraining.java’ saved [943/943]

                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/vault-door-training]
└─$ cat VaultDoorTraining.java 
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
        Scanner scanner = new Scanner(System.in); 
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
   }

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_be8d9806f18");
    }
}
```

## Bandera
picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}

## Notas adicionales
>[!tip]
>**Ingeniería inversa**
>Es un proceso o método mediante el cual se intenta comprender a través del razonamiento deductivo cómo un dispositivo, proceso, sistema o programa informático previamente fabricado realiza una tarea con muy poca (o ninguna) idea de cómo lo hace exactamente.

## Referencias
[Reverse engineering](https://en.wikipedia.org/wiki/Reverse_engineering)