Campos que no tienen absolutamente ningún dato en la tabla, nosotros indicamos al crear una tabla si contendrá valores obligatoriamente (NOT NULL) o si ese campo puede estar vacío (NULL)

```SQL
CREATE TABLE nombreTabla (
campo1 varchar(20) not null,
campo2 number
...
);
```

### Consultas NULL:

Para consultar valores `NULL` no podemos usar los operadores comunes si no que tenemos que usar la palabra clave `IS NULL`

```SQL
SELECT * FROM nombreTabla WHERE campo IS NULL;
```

### Consultas NOT NULL:

Para consultar valores que no sean `NULL`, usaremos la palabra clave `IS NOT NULL`

```SQL
SELECT * FROM nombreTabla WHERE campo IS NOT NULL;
```
