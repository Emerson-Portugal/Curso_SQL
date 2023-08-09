# Modificion de los Parametros de una Tabla

En este Modulo te voy a enseñar a como alterar o modificar los parametros de entrada de una tabla

## Tabla de Ejemplo 
```sql
create table perfil(
    id serial primary key,
    nombre varchar(50),
    apellido varchar(50),
    edad integer
);
```

## Modificar el Nombre de una Tabla
Este comando renombrará la tabla `perfil` a `perfil_usuario`.
```sql
ALTER TABLE perfil RENAME TO perfil_usuario;
```
## Modificar el Nombre de una Columna
Esto cambiará el nombre de la columna `nombre` en la tabla perfil a `nombre_completo`.
```sql
ALTER TABLE perfil RENAME COLUMN nombre TO nombre_completo;
```
## Agregar un Nueva Columna a la Tabla
Agregará una nueva columna llamada `fecha` con el tipo de datos `DATE` a la tabla perfil.
```sql
ALTER TABLE perfil ADD COLUMN fecha DATE;
```

## Eliminar una Columna de la Tabla
Eliminará la columna `fecha` de la tabla perfil.
```sql
ALTER TABLE perfil DROP COLUMN fecha;
```

## Cambiar el tipo de Datos de una Columna
Cambiará el tipo de `datos` de la columna fecha en la tabla perfil a `varchar(50)`.

```sql
ALTER TABLE perfil ALTER COLUMN fecha SET DATA TYPE varchar(50);
```

## Eliminar una Tabla
Esto eliminará completamente la tabla perfil y todos sus datos asociados.

```sql
DROP TABLE perfil;
```