La palabra clave `DELETE` sirve para borrar valores/registros, suele ir acompañada de una condición `WHERE` ya que si hacemos un:

```sql
DELETE FROM nombreTabla 
```

Borramos absolutamente todos los registros de la tabla

Por lo que como la usaríamos para borrar un registro especifico:

```sql
DELETE FROM nombreTabla WHERE condicion;
```

