Nos devuelve los 4 primeros caracteres desde la izquierda, si indicamos mas de lo que hay repite caracteres:

```sql
SELECT LPAD('Hello', 4, 'World') FROM DUAL;
-- Nos devolvera "Hell"
```