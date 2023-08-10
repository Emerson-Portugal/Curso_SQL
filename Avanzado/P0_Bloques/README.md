# Introduccion a Bloques
En este modulo te a enseñar a como es la estrucctura de un Bloque, como se declara varibles y como cual es la funcionalidad principal

## Estucctura de un Bloque 

```sql
do
$$
declare
-- declaracion de variables
begin
-- condicionales
end;
$$
```
## Ejemplos de Estuccturas de un Bloque

- Bloque Simple

```sql
do
$$
begin
    raise notice 'Hola Mundo';
end;
$$
```

- Bloque con Declaraciones
```sql
DO
$$
DECLARE
    nombre varchar(50) := 'emersoncrp';
BEGIN
    RAISE NOTICE 'Mi nombre es: %', nombre;
END;
$$;

```
- Bloque con Declaraciones, condicionales y Almacenamiento 

```sql
do
$$
declare
    nuevo_nombre varchar(50);
begin
    select nombre 
    into nuevo_nombre
    from pefil;
    raise notice 'Este es tu nombre: %', nuevo_nombre;
end;
$$
```