El operador `LIKE` es usado dentro de un condición `WHERE` para buscar un patrón especifico en una columna existen 2 comodines que se usan con el `LIKE` el `%` y el `_`

```sql
SELECT * FROM Customers  
WHERE CustomerName LIKE 'a%'; -- Devuelve lo que empieze por 'a'
```

```sql
SELECT * FROM Customers  
WHERE CustomerName LIKE '%a'; -- Devuelve lo que termine por 'a'
```

```sql
SELECT * FROM Customers  
WHERE CustomerName LIKE '%a%'; -- Devuelve lo que contenga 'a'
```

```sql
SELECT * FROM Customers
WHERE City LIKE 'L_nd__'; -- Devuelve lo que contenga la condicion
```