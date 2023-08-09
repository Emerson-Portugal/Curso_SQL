# Creacion de Tablas

## Definicion de una Tabla
Primero debemos crear la tabla donde se va se almecerara la infomacion, ademas se debe definir un nombre para esta tabla

```sql
create table perfil(
-- Datos 
);
```

## Definir los parametros para la Tabla

Aqui vamos a definir todo los valores que va a poder almacener nuestra tabla

```sql
create table perfil(
    id serial primary key,
    nombre varchar(50),
    apellido varchar(50),
    edad integer
);
```

## Insertar valores a la tabla 

Teniendo en cuenta los paramtros que puede resivir nuestra tabla, vamos a porceder a insertar valores a la tabla ya creada

```sql
insert into perfil(nombre,apellido,edad) values ('Juan', 'Perez', 25);
```

## Mostrar los valores Ingresados

Con un simple comando vamos a mostrar todo los valores ingresados en la tabla

```sql
select * from perfil
```
