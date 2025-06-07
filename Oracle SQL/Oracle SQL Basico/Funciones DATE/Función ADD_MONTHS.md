Esta función agrega meses a una fecha

```sql
SELECT add_months(to_date('10/10/2020', 'dd/mm/yyyy'),5) FROM DUAL
-- Nos devolvera 10-MAR-21

SELECT add_months(to_date('10/10/2020', 'dd/mm/yyyy'),-5) FROM DUAL
-- Nos devolvera 10-05-2020
```