Nos devolverá el numero de meses que hay entre una fecha y otra

```sql
SELECT MONTHS_BETWEEN(TO_DATE('19/05/2020', 'DD/MM/YYYY', TO_DATE('19/08/2020', 'DD/MM/YYYY')) FROM DUAL;
-- Nos devolvera -3
```
