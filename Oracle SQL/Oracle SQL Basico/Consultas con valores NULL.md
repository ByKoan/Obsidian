Podremos realizar consultas para descubrir los registros que tienen valores NULL y los que no

```sql
SELECT * 
FROM tabla
WHERE campo IS NULL;
```

```sql
SELECT * 
FROM tabla
WHERE campo IS NOT NULL;
```