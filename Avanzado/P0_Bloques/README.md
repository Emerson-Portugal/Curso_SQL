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

## Identificador del Tipo de Dato

```sql
do 
$$
declare
    nuevo_titulo pelicula.titulo%type;
begin

    select titulo
    from pelicula
    into nuevo_titulo
    where pelicula_id = 100;


    raise notice 'Este es el Titulo del id 100: %s', nuevo_titulo;
end; 
$$
```
## Bloques y Sub Bloques


```sql
do 
$$
declare
    contador integer := 0;
begin
    contador := contador + 1;
    raise notice 'Este es el Valor%', contador;
    declare
        contador integer := 0;
    begin
        contador := contador + 10;
        raise notice 'Valor Actual del Bloque %', contador;
        raise notice 'Valor del Bloque Anterior %', outer_block.contador;
    end;
end;
$$ ;
```

## Seleccion del Valor por Fila
```sql
do 
$$
declare
    seleccionar_actor actor%rowtype;
begin

    select *
    from actor
    into seleccionar_actor
    where actor_id = 10;

    raise notice 'Este es el Nombre del Actor % %', seleccionar_actor.nombre, seleccionar_actor.apellido;
end;
$$
```

## Seleccion del Valor por Tabla

```sql
Do 
$$
Declare 
    rec record;
Begin
    for rec in 
    select titulo, duracion from pelicula where duracion > 50 order by duracion 
    loop
        raise notice '% (%)', rec.titulo, rec.duracion;
    end loop;
end;
$$
```