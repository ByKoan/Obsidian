Nos devuelve todas las filas de las 2 tablas mostrando:

- Las filas que coincidan en ambas tablas
- Las filas que solo coincidan en la izquierda
- Las filas que solo coincidan en la derecha

```sql
SELECT *
FROM tabla1
FULL JOIN tabla2
ON tabla1.campo1 = tabla2.campo2;
```