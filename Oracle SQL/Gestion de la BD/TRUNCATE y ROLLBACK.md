**ROLLBACK** sirve para cuando hemos eliminado datos con un **DELETE FROM** y queremos recuperar esos datos **(SI HACEMOS COMMIT DESPUES DEL DELETE FROM NO SE PODRA HACER ROLLBACK)**

```SQL
DELETE FROM tabla
ROLLBACK; -- Nos devuelve los datos de la tabla
```

**TRUNCATE** Elimina los datos al igual que **DELETE FROM** pero este hace **COMMIT** por lo que no podremos usar **ROLLBACK**

```SQL 
TRUNCATE tabla;
```
