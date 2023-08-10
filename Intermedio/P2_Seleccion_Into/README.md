# Seleccion con INTO para Tablas
En este modulo te voy a enseñar a como selecionar valores y guardarlos en variables o tablas temporales, esto nos permitira un mayor control y organizacion de los valores. La unica condicion es que la misma cantidad valores se van a guardar, tiene que ser igual al usar `INTO`.

## Seleccion y Almacenamiento en una Tabla

```sql
create table Perfil_Nuevo(
    id serial primary key,
    nombre varchar(50),
    apellido varchar(50),
    edad integer
);
```
```sql
INSERT INTO Perfil_Nuevo (id, nombre, apellido)
SELECT id, nombre, apellido
FROM Perfil
```

## Seleccion y Almacenamiento en una Tabla Temporal

```sql
SELECT nombre, apellido
INTO TEMPORARY TABLE Perfil_Nuevo_1
FROM Perfil
WHERE id > 5;
```
```sql
SELECT * FROM Perfil_Nuevo_1;
```