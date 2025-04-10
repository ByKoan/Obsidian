La mayor parte de veces que concatenaremos columnas será para tener junto 2 o mas columnas en una consulta

```sql
SELECT CAMPO1 || ' ' || CAMPO2, CAMPO3...
FROM nombreTabla;
```

### Usando función `CONCAT`:

```sql
SELECT CONCAT (CAMPO1, CAMPO2) 
FROM nombreTabla;
```
