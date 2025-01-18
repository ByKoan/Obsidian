El operador ``IN`` le permite especificar múltiples valores en una condición ``WHERE``.

El operador IN es una abreviatura de múltiples condiciones ``OR``.

```sql
SELECT * FROM Customers  
WHERE Country IN ('Germany', 'France', 'UK'); 
-- Solo nos devuelve lo que contenga la condicion
```

### NOT IN:
Misma función que el operador ``IN`` pero al revés, que no contenga la condición dada

```sql
SELECT * FROM Customers  
WHERE Country NOT IN ('Germany', 'France', 'UK');
```