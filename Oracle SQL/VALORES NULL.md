Si en el data modeler indicamos que el campo no era obligatorio pueden existir valores nulos si no le asignamos ningún tipo de valor 

Tenemos 2 operadores para datos NULL:
- IS NULL (Es nulo):
```sql
SELECT CustomerName, ContactName, Address  
FROM Customers  
WHERE Address IS NULL;
```
- IS NOT NULL (No es nulo):
```sql
SELECT CustomerName, ContactName, Address  
FROM Customers  
WHERE Address IS NOT NULL;
```
