### SQL Create DB:

```SQL
CREATE DATABASE nombre de la base; -- Crear una base de datos
```

### SQL Drop DB:

```SQL
DROP DATABASE nombre de la base; -- Eliminar una base de datos
```

### SQL BackUp DB:

```SQL
BACKUP DATABASE nombre de la base; -- Hacer Back UP
TO DISK = 'filepath'; -- A la ruta x
```

### SQL Create Table:

```sql
CREATE TABLE nombre de la tabla (
	nombre columna tipo,
	nombre columna tipo,
	nombre columna tipo,
	...
) -- Creacion de tablas
```

### SQL Drop Table:

```sql
DROP TABLE nombre tabla; -- Eliminar tabla 
TRUNCATE TABLE nombre tabla; -- Eliminar datos de la tabla
```

### SQL Alter Table:

```sql
ALTER TABLE nombre tabla; -- Modificar columnas de una tabla
ADD nombre columna tipo;
```

### Constraint:

```sql
CREATE TABLE nombre de tabla (
	columna 1 tipo constraint, -- Restricciones
	columna 2 tipo constraint,
	columna 3 tipo constraint,
	....
)
```

### Not NULL:

```SQL
CREATE TABLE Persons (
	ID int NOT NULL, -- No puede estar vacio
	LastName varchar(255) NOT NULL,
	FirstName varchar(255) NOT NULL,
	Age int
)
```

### Primary Key:

```sql
CREATE TABLE Persons (  
    ID int NOT NULL PRIMARY KEY, -- Clave primaria de la tabla
    LastName varchar(255) NOT NULL,  
    FirstName varchar(255),  
    Age int  
);
```

### Foreign Key:

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID) -- Clave extrangera
);
```

### SQL Check:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int CHECK (Age>=18) -- Comprobar
);
```

### SQL Default:

```sql
CREATE TABLE Persons (  
    ID int NOT NULL,  
    LastName varchar(255) NOT NULL,  
    FirstName varchar(255),  
    Age int,  
    City varchar(255) DEFAULT 'Sandnes' -- Por defecto
);
```

### SQL Create Index:

```sql
CREATE INDEX index_name -- Crear un Indice
ON table_name (column1, column2, ...); 
```

### SQL AutoIncrement:
