# vault-door-3

## Descripción
Esta bóveda utiliza bucles for y matrices de bytes. El código fuente de esta bóveda está aquí: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/943ea40e3f54fca6d2145fa7aadc5e09/VaultDoor3.java)

## Pistas
- Haz una tabla que contenga cada valor de las variables del bucle y el correspondiente índice del buffer en el que escribe

## Solución
Código original de la bóveda:
```java
import java.util.*;

class VaultDoor3 {
    public static void main(String args[]) {
        VaultDoor3 vaultDoor = new VaultDoor3();
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

    // Our security monitoring team has noticed some intrusions on some of the
    // less secure doors. Dr. Evil has asked me specifically to build a stronger
    // vault door to protect his Doomsday plans. I just *know* this door will
    // keep all of those nosy agents out of our business. Mwa ha!
    //
    // -Minion #2671
    public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm18g947_u_4_m9r54f");
    }
}
```

Código modificado para obtener la bandera:
```java
public class VaultDoor3 {  
    public static void main(String[] args) {  
        VaultDoor3 vaultDoor = new VaultDoor3();  
        System.out.println(vaultDoor.checkPassword("jU5t_a_sna_3lpm18g947_u_4_m9r54f"));  
    }  
  
    public String checkPassword(String password) {  
        char[] buffer = new char[32];  
        int i;  
        for (i=0; i<8; i++) {  
            buffer[i] = password.charAt(i);  
        }  
        for (; i<16; i++) {  
            buffer[i] = password.charAt(23-i);  
        }  
        for (; i<32; i+=2) {  
            buffer[i] = password.charAt(46-i);  
        }  
        for (i=31; i>=17; i-=2) {  
            buffer[i] = password.charAt(i);  
        }  
        return new String(buffer);  
    }  
}
```

## Bandera
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}

## Notas adicionales
Como se puede apreciar, el código fue reutilizado pero en lugar de aplicarle el método `checkPassword()` a un input del usuario, se le aplicó a la cadena a comparar al final del código sin modificar.

## Referencias