Nos quita los caracteres de la izquierda que indiquemos nosotros

```sql
SELECT LTRIM('Hello world', 'Hell') FROM DUAL;
-- Nos devolvera "o world"
```