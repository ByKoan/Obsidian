Consultas anidadas dentro de otra consulta.

-  Subconsultas de 1 solo registro

```sql 
SELECT CAMPO
FROM TABLA
WHERE CAMPOCONDICION > ( SELECT AVG(CAMPOCONDICION)
						 FROM TABLA
);
```

- Subconsultas de tabla completa (devuelve múltiples columnas o se usa como una tabla)

```sql
SELECT *
FROM (
	SELECT CAMPO1, CAMPO2
	FROM TABLA
	WHERE CAMPO2 > VALOR
) SUB
WHERE CAMPO2 < VALOR;
```