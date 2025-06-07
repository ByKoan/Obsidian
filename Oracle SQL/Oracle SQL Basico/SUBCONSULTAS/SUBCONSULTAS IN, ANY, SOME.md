Subconsultas con valores alternos o valores específicos

- Alguno en la lista

```sql
SELECT CAMPO1, CAMPO2 
FROM TABLA
WHERE CAMPO3 IN (
	SELECT CAMPO1
	FROM TABLA2
	WHERE CAMPO2 IN ('Valor1', 'Valor2', 'Valor3')
);
```

- Cualquiera

```sql
SELECT CAMPO1 
FROM TABLA
WHERE CAMPO2 = ANY (
	SELECT CAMPO1
	FROM TABLA2
	WHERE CAMPO2 LIKE '%Valor'
);
```

- Alguno

```sql
SELECT CAMPO1 
FROM TABLA
WHERE CAMPO2 = SOME (
	SELECT CAMPO1
	FROM TABLA2
	WHERE CAMPO2 LIKE '%Valor'
);
```
