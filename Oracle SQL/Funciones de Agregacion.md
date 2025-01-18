### MIN y MAX:
Devuelve el valor mínimo o máximo de una columna

```sql
SELECT MIN(Price)
FROM Products;
```

```sql
SELECT MAX(Price)
FROM Products; 
```
### COUNT:
Devuelve el numero de lo que haya contado (La condición que le hayamos puesto):

```sql
SELECT COUNT(*) -- Cuenta todo
FROM Products;
```

Se puede sumar con un `SELECT DISTINCT` para ignorar duplicados

```SQL
SELECT COUNT(DISTINCT Price)  
FROM Products;
```
### SUM:
La función SUMA() devuelve la suma total de una columna numérica.

```SQL
SELECT SUM(Quantity)  
FROM OrderDetails;
```
### AVG:
Devuelve la media de la condición especificada:

```sql
SELECT AVG(Price)  
FROM Products;
```