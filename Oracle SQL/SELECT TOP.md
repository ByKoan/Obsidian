Es útil ya que nos devuelve los primeros casos que le indiquemos, ejemplo:

```sql
SELECT TOP 3 * FROM Customers;
```

En Oracle SQL se hace de la siguiente forma:

```sql
SELECT column_name(s) 
FROM table_name  
ORDER BY column_name(s)  
FETCH FIRST number ROWS ONLY;
```
