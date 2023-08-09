# Edicion de Tablas

En este punto te voy a se va a enserñar mostrar, modificar y almacenar los valores de una tabla para que de esta manera se pueda trabajar de una manera mas ordenada.

## Ejemplos Base
Vamos a tener una tabla fija, donde vamos a trabajar con estos valores

```sql
create table perfil(
    id serial primary key,
    nombre varchar(50),
    apellido varchar(50),
    edad integer
);
```

## Actualizacion de valores de una Tabla
Aqui vamos a actualizar uno o todo los valores ingresados de una tabla 

- Modificacion de todos los Valores de una tabla

```sql
update perfil set nombre = 'Juan';
```

- Modificacion de un valor Especifico de una tabla

```sql
update perfil set nombre = 'Juan' where id = 1;
```

## Eliminacion de Valores de una Tabla
Aqui vamos a eliminar uno o todo los valores de una tabla ya ingresados

- Eliminacion  de todos los Valores de una tabla

```sql
delete from perfil;
```

- Eliminacion de un valor Especifico de una tabla

```sql
delete from perfil where id = 1;
```

## Mostrar los valores de una Tabla

- Listar Todo los registros que hemos ingresado
```sql
Select * from perfil;
```
- Listar solo un elemento que nosotros indicamos
```sql
Select * from perfil where id = 1;
```
- Limitar la cantidad de elemento que vamos a nosotrar
```sql
Select * from perfil limit 1;
```
- Muestra los valores que cumplan las condiciones
    - Con una condicciones
    ```sql
    Select * from perfil where edad > 18;
    ```
    - Con dos a mas condicciones
    ```sql
    Select * from perfil where edad > 18 and id = 1;
    ```
- Muestra todo los valores de la tabla, excepto los valores indicados por `!=`
```sql
Select * from perfil where edad != 20;
```
- Muestra todo los valores de la tabla que esten en el rango
```sql
Select * from perfil where edad between 15 and 20;
```
- Muestra todo los valores que tengan la el valos definidos

    - Muestra todas las cadenas de texto que tengan `la letra A`

    ```sql
    Select * from perfil where nombre like %a%;
    ```
    - Muestra todas las cadenas de texto que terminen con `una letra A`

    ```sql
    Select * from perfil where nombre like %a;
    ```
    - Muestra todas las cadenas de texto que comienzan con `una letra A`

    ```sql
    Select * from perfil where nombre like a%;
    ```                                                             
- Muestra todo los valores de forma acendente
```sql
Select * from perfil order by edad asc;
```  
- Muestra todo los valores de forma decendente
```sql
Select * from perfil order by edad desc;
```   
- Solo muestra los valores de nuestro interes
    - Nombre Tabla
    ```sql
    Select nombre, edad from perfil;
    ``` 
    - Alias
    ```sql
    Select nombre as nombre_completo from perfil;
    ``` 
- Muestra solo el mayor
```sql
Select max(edad) as mayor_edad from perfil;
```   
- Muestra solo el menor
```sql
Select min(edad) as menor_edad from perfil;
```   
- Muestra el promedio
```sql
Select avg(edad) as promedio_edad from perfil;
```   

