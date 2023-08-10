# Excepciones
En este modulo te enseñare a como usar el Excepciones en SQL, esto nos va a permitir poder controlar los errores que podemos cometer a la hora de escribir codigo SQL, esto es de gran ayuda, para no eliminar la Base de Datos.

## Estructura de una Excepcion

```sql
DO
$$
declare
begin
    statements;
exception
    when condition [or condition...] then
        handle_exception;
    [when condition [or condition...] then
        handle_exception;]
    [when others then
        handle_other_exceptions;]
end;
$$
```
## Excepcion no_data_found
```sql
do
$$
declare
    rec record;
    v_film_id int = 2000;
begin
-- select a film
    select film_id, title
    into strict rec
    from film
    where film_id = v_film_id;
-- catch exception
exception
    when no_data_found then
        raise exception 'film % not found', v_film_id;
end;
$$
language plpgsql;
```