### AND:
- Lo usaremos cuando queramos indicar mas de una condición
```sql
SELECT *  
FROM Customers  
WHERE Country = 'Spain' AND CustomerName LIKE 'G%';
```
### OR:
- Lo usaremos cuando queramos que se de una expresión **O** otra
```sql
SELECT *  
FROM Customers  
WHERE Country = 'Germany' OR Country = 'Spain';
```
### NOT:
- Lo usaremos cuando queramos que no nos de una condición.
```sql
SELECT * FROM Customers  
WHERE NOT Country = 'Spain';
```
