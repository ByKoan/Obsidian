Nos sirve para comparar campos que coincidan con un valor, disponemos también del operador
**NOT LIKE**

```sql
SELECT *
FROM TABLA
WHERE CAMPO LIKE '%Valor%';
```

```sql
SELECT *
FROM TABLA
WHERE CAMPO LIKE '%Valor'; -- Termine con 'Valor'
```

```sql
SELECT *
FROM TABLA
WHERE CAMPO LIKE 'Valor%'; -- Empieze con 'Valor'
```
