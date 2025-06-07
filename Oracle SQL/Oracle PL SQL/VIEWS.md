Son el resultado de consultas guardadas con un nombre de tal forma que podamos acceder a ellas como una tabla virtual. No almacenan datos por si solas, si no que muestra los resultados de una consulta cada vez que se accede.

```sql
CREATE VIEW nombreVista AS
SELECT *
FROM tabla
WHERE condiciones;
```

```sql
SELECT *
FROM nombreVista;
```
