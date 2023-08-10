# Condiccionales en SQL (POSTGRESQL)
En este modulo te voy a enseñar a usar las condicionales `IF`, `IF-ELSE`, `WHILE`, `DO-WHILE` y `FOR` porque como sabemos SQL es un Lenguaje de Programacion.

## Condiccional IF/ELSIF/IF-ELSE

### IF
```sql
DO
$$
DECLARE
    nombre varchar(50) := 'emersoncrp';
BEGIN
    IF nombre == 'emersoncrp' then
        RAISE NOTICE 'Mi nombre es: %', nombre;
    END IF;
END;
$$;

```

### IF-ELSE
```sql
DO
$$
DECLARE
    nombre varchar(50) := 'emersoncrp';
BEGIN
    IF nombre == 'emersoncrp' then
        RAISE NOTICE 'Mi nombre es: %', nombre;
    ELSE
        RAISE NOTICE 'Nombre incorrectp'
    END IF;
END;
$$;

```
### IF-ELSIF-ELSE
```sql
DO
$$
DECLARE
    nombre varchar(50) := 'emerson';
BEGIN
    IF nombre == 'emersoncrp' then
        RAISE NOTICE 'Mi nombre es: %', nombre;
    ELSIF nombre == 'emersoncrp' then
        RAISE NOTICE 'Mi nombre es: %', nombre;
    ELSE
        RAISE NOTICE 'Nombre incorrectp'
    END IF;
END;
$$;

```

## Condiccional WHILE

```sql
DO
$$
DECLARE
    contador integer := 0;
BEGIN
    WHILE contador <= 10 LOOP
        RAISE NOTICE 'Valor: %', contador;
        contador = contador + 1;
    END LOOP;
END;
$$;

```

## Condiccional FOR

```sql
DO
$$
DECLARE
    contador integer := 0;
BEGIN
    FOR contador in  10 LOOP
        RAISE NOTICE 'Valor: %', contador;
        contador = contador + 1;
    END LOOP;
END;
$$;
```