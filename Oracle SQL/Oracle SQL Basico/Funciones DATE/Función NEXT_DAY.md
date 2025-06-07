Nos devolverá el siguiente día que sea X de la fecha que le indiquemos

```sql
SELECT NEXT_DAY(TO_DATE('10/08/2020', 'DD/MM/YYYY'), 'MONDAY') FROM DUAL;
-- Nos devolvera 17-AUG-20
```