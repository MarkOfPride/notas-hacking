# SQL Direct

## Descripción
¡Conéctese a este servidor PostgreSQL y encuentre la bandera!
`psql -h saturn.picoctf.net -p 65501 -U postgres pico`
La contraseña es `postgres` 

## Pistas
- ¿Qué contiene una base de datos SQL?

## Solución
```bash
markofpride-picoctf@webshell:~$ psql -h saturn.picoctf.net -p 57396 -U postgres pico
Password for user postgres: 
psql (14.5 (Ubuntu 14.5-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
Type "help" for help.

pico=# SELECT * FROM 
flags                information_schema.  pg_catalog.          pg_toast.            public.              
pico=# SELECT * FROM FLAGS;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# ^Z
```

## Bandera
picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}

## Notas adicionales
| Comando | Descripción |
|--------|--------|
| SELECT | La instrucción SELECT en SQL se usa para recuperar datos de una base de datos relacional |

## Referencias
[PostgreSQL SELECT](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-select/)