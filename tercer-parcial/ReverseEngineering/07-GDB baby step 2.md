# GDB baby step 2

## Descripción
¿Puedes averiguar qué hay en el registro `eax` al final de la función `main`? Pon tu respuesta en el formato picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su bandera sería `picoCTF{17}`.
Depura [esto](https://artifacts.picoctf.net/c/520/debugger0_b).

## Pistas
- Puede calcular `eax` usted mismo, o puede establecer un punto de interrupción para después del cálculo e inspeccionar `eax` para dejar que el programa haga el trabajo pesado por usted.

## Solución
```bash
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep2]
└─$ chmod +x debugger0_b
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep2]
└─$ gdb debugger0_b -q
GEF for linux ready, type `gef' to start, `gef config' to configure
88 commands loaded and 5 functions added for GDB 13.1 in 0.00ms using Python engine 3.11
Reading symbols from debugger0_b...
(No debugging symbols found in debugger0_b)
gef➤  disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   rbp
   0x000000000040110b <+5>:     mov    rbp,rsp
   0x000000000040110e <+8>:     mov    DWORD PTR [rbp-0x14],edi
   0x0000000000401111 <+11>:    mov    QWORD PTR [rbp-0x20],rsi
   0x0000000000401115 <+15>:    mov    DWORD PTR [rbp-0x4],0x1e0da
   0x000000000040111c <+22>:    mov    DWORD PTR [rbp-0xc],0x25f
   0x0000000000401123 <+29>:    mov    DWORD PTR [rbp-0x8],0x0
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    eax,DWORD PTR [rbp-0x8]
   0x000000000040112f <+41>:    add    DWORD PTR [rbp-0x4],eax
   0x0000000000401132 <+44>:    add    DWORD PTR [rbp-0x8],0x1
   0x0000000000401136 <+48>:    mov    eax,DWORD PTR [rbp-0x8]
   0x0000000000401139 <+51>:    cmp    eax,DWORD PTR [rbp-0xc]
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    eax,DWORD PTR [rbp-0x4]
   0x0000000000401141 <+59>:    pop    rbp
   0x0000000000401142 <+60>:    ret
End of assembler dump.
gef➤  break *0x401141
Breakpoint 1 at 0x401141
gef➤  run
Starting program: /home/kali/picoctf/reversing/GDBbabystep2/debugger0_b 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x0000000000401141 in main ()
[ Legend: Modified register | Code | Heap | Stack | String ]
───────────────────────────────────────────────────────────────────────────────────────────────── registers ────
$rax   : 0x4af4b           
$rbx   : 0x00007fffffffdec8  →  0x00007fffffffe21a  →  "/home/kali/picoctf/reversing/GDBbabystep2/debugger[...]"
$rcx   : 0x00007ffff7f9e820  →  0x00007ffff7fa02e0  →  0x0000000000000000
$rdx   : 0x00007fffffffded8  →  0x00007fffffffe250  →  "COLORFGBG=15;0"
$rsp   : 0x00007fffffffddb0  →  0x0000000000000001
$rbp   : 0x00007fffffffddb0  →  0x0000000000000001
$rsi   : 0x00007fffffffdec8  →  0x00007fffffffe21a  →  "/home/kali/picoctf/reversing/GDBbabystep2/debugger[...]"
$rdi   : 0x1               
$rip   : 0x0000000000401141  →  <main+59> pop rbp
$r8    : 0x00000000004011c0  →  <__libc_csu_fini+0> endbr64 
$r9    : 0x00007ffff7fcf6a0  →  <_dl_fini+0> push rbp
$r10   : 0x00007ffff7fcb878  →  0x000c00120000000e
$r11   : 0x00007ffff7fe18c0  →  <_dl_audit_preinit+0> mov eax, DWORD PTR [rip+0x1b552]        # 0x7ffff7ffce18 <_rtld_global_ro+888>
$r12   : 0x0               
$r13   : 0x00007fffffffded8  →  0x00007fffffffe250  →  "COLORFGBG=15;0"
$r14   : 0x0               
$r15   : 0x00007ffff7ffd020  →  0x00007ffff7ffe2e0  →  0x0000000000000000
$eflags: [ZERO carry PARITY adjust sign trap INTERRUPT direction overflow resume virtualx86 identification]
$cs: 0x33 $ss: 0x2b $ds: 0x00 $es: 0x00 $fs: 0x00 $gs: 0x00 
───────────────────────────────────────────────────────────────────────────────────────────────────── stack ────
0x00007fffffffddb0│+0x0000: 0x0000000000000001   ← $rsp, $rbp
0x00007fffffffddb8│+0x0008: 0x00007ffff7df318a  →  <__libc_start_call_main+122> mov edi, eax
0x00007fffffffddc0│+0x0010: 0x0000000000000000
0x00007fffffffddc8│+0x0018: 0x0000000000401106  →  <main+0> endbr64 
0x00007fffffffddd0│+0x0020: 0x0000000100000000
0x00007fffffffddd8│+0x0028: 0x00007fffffffdec8  →  0x00007fffffffe21a  →  "/home/kali/picoctf/reversing/GDBbabystep2/debugger[...]"                                                                                             
0x00007fffffffdde0│+0x0030: 0x00007fffffffdec8  →  0x00007fffffffe21a  →  "/home/kali/picoctf/reversing/GDBbabystep2/debugger[...]"                                                                                             
0x00007fffffffdde8│+0x0038: 0xbb289d8e343dd951
─────────────────────────────────────────────────────────────────────────────────────────────── code:x86:64 ────
     0x401139 <main+51>        cmp    eax, DWORD PTR [rbp-0xc]
     0x40113c <main+54>        jl     0x40112c <main+38>
     0x40113e <main+56>        mov    eax, DWORD PTR [rbp-0x4]
●→   0x401141 <main+59>        pop    rbp
     0x401142 <main+60>        ret    
     0x401143                  cs     nop WORD PTR [rax+rax*1+0x0]
     0x40114d                  nop    DWORD PTR [rax]
     0x401150 <__libc_csu_init+0> endbr64 
     0x401154 <__libc_csu_init+4> push   r15
─────────────────────────────────────────────────────────────────────────────────────────────────── threads ────
[#0] Id 1, Name: "debugger0_b", stopped 0x401141 in main (), reason: BREAKPOINT
───────────────────────────────────────────────────────────────────────────────────────────────────── trace ────
[#0] 0x401141 → main()
────────────────────────────────────────────────────────────────────────────────────────────────────────────────
gef➤  info registers
rax            0x4af4b             0x4af4b
rbx            0x7fffffffdec8      0x7fffffffdec8
rcx            0x7ffff7f9e820      0x7ffff7f9e820
rdx            0x7fffffffded8      0x7fffffffded8
rsi            0x7fffffffdec8      0x7fffffffdec8
rdi            0x1                 0x1
rbp            0x7fffffffddb0      0x7fffffffddb0
rsp            0x7fffffffddb0      0x7fffffffddb0
r8             0x4011c0            0x4011c0
r9             0x7ffff7fcf6a0      0x7ffff7fcf6a0
r10            0x7ffff7fcb878      0x7ffff7fcb878
r11            0x7ffff7fe18c0      0x7ffff7fe18c0
r12            0x0                 0x0
r13            0x7fffffffded8      0x7fffffffded8
r14            0x0                 0x0
r15            0x7ffff7ffd020      0x7ffff7ffd020
rip            0x401141            0x401141 <main+59>
eflags         0x246               [ PF ZF IF ]
cs             0x33                0x33
ss             0x2b                0x2b
ds             0x0                 0x0
es             0x0                 0x0
fs             0x0                 0x0
gs             0x0                 0x0
gef➤  quit
                                                                                                                
┌──(kali㉿kali)-[~/picoctf/reversing/GDBbabystep2]
└─$ python3
Python 3.10.8 (main, Nov  4 2022, 09:21:25) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x4af4b)
307019
>>> exit()
```

>[!solution]
>Para resolver este reto, primero se le dieron permisos de ejecución al archivo dado, luego se desensambló su función `main()` usando `gdb`, posteriormente se colocó un breakpoint justo antes del fin de la ejecución y se vió el contenido de todos los registros, el que nos interesa tenia el valor de `0x4af4b` que en decimal equivale a 307019, nuestra bandera.

## Bandera
picoCTF{307019}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| gdb | El depurador de GNU, su propósito es permitirle ver lo que está pasando ''dentro'' de otro programa mientras se ejecuta-o lo que otro programa estaba haciendo en el momento en que se bloqueó. |

## Referencias
[gdb(1) - Linux man page](https://linux.die.net/man/1/gdb)