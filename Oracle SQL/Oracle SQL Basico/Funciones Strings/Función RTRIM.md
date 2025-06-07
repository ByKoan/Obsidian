Nos quita los caracteres de la derecha que indiquemos nosotros

```sql
SELECT RTRIM('Hello World', 'orld') FROM DUAL;
-- Nos devolvera "Hello W"
```