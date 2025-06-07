Nos devuelve el ultimo día del mes que contenga la fecha

```sql
SELECT LAST_DAY(TO_DATE('09/02/2020', 'dd/mm/yyyy')) FROM DUAL;
-- Nos devolvera 29/02/20
```