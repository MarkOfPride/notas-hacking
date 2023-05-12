# reverse_cipher

## Descripción
Hemos recuperado un archivo [binario](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev) y uno de [texto](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev_this). Puede invertir la bandera.

## Pistas
- objdump y Gihdra son algunas herramientas que podrían ayudar con esto

## Solución
Para comenzar, se utilizó el programa "Ghidra" para convertir el binario dado a lo más parecido a lenguaje C, a continuación se muestra el código resultante (algunas variables tienen el nombre cambiado para facilitar el entendimiento)

```C
void main(void)

{
  size_t sVar1;
  char flag [23];
  char local_41;
  int local_2c;
  FILE *flagrev;
  FILE *flagfile;
  uint j;
  int i;
  char rev;
  
  flagfile = fopen("flag.txt","r");
  flagrev = fopen("rev_this","a");
  if (flagfile == (FILE *)0x0) {
    puts("No flag found, please make sure this is run on the server");
  }
  if (flagrev == (FILE *)0x0) {
    puts("please run this on the server");
  }
  sVar1 = fread(flag,0x18,1,flagfile);
  local_2c = (int)sVar1;
  if ((int)sVar1 < 1) {
                    /* WARNING: Subroutine does not return */
    exit(0);
  }
  for (i = 0; i < 8; i = i + 1) {
    rev = flag[i];
    fputc((int)rev,flagrev);
  }
  for (j = 8; (int)j < 0x17; j = j + 1) {
    if ((j & 1) == 0) {
      rev = flag[(int)j] + '\x05';
    }
    else {
      rev = flag[(int)j] + -2;
    }
    fputc((int)rev,flagrev);
  }
  rev = local_41;
  fputc((int)local_41,flagrev);
  fclose(flagrev);
  fclose(flagfile);
  return;
}
```

Dado este código, se adaptó un script en python para lograr decodificar la bandera codificada contenida en en el archivo `rev_this`:

```python
cifrado = open('rev_this', 'r').read()
print(cifrado)

flag = ''

for i in range(8, len(cifrado)-1):
        if i & 1 == 0:
                flag += chr(ord(cifrado[i]) - 5)
        else:
                flag += chr(ord(cifrado[i]) + 2)

print(flag)
```

## Bandera
picoCTF{r3v3rs36ad73964}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| Ghidra | Conjunto de herramientas de ingeniería inversa de software (SRE) desarrolladas por la Dirección de Investigación de la NSA en apoyo de la misión de Ciberseguridad |

## Referencias
[Ghidra](https://ghidra-sre.org/)
