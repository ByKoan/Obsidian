Los Alias son palabras clave que nos sirven para identificar una columna en la consulta cuando no queremos que tenga el nombre predeterminado que Oracle nos devuelve (Cambiarla el nombre).

Para cambiar una columna de nombre usamos la palabra clave `AS`

```sql
SELECT CAMPO1 AS "Este es el campo 1", CAMPO2 ...
FROM nombreTabla
```

Si queremos asignar un alias a una tabla lo haríamos de la siguiente forma

```sql
SELECT CAMPO1 AS "Este es el campo 1", CAMPO2 ...
FROM nombreTabla N
```