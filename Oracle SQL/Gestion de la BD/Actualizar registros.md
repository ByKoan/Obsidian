Con **UPDATE** podremos actualizar campos de registros

```sql
UPDATE tabla SET campo = 'nuevo valor';
-- Afecta a toda la tabla
```

```sql
UPDATE tabla SET campo = 'nuevo valor' WHERE campo = condicion;
```

```sql
UPDATE articulos SET nombre WHERE codigo = 8;
```
