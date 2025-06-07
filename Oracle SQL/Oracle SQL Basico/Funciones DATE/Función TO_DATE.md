Pasa un campo de formato `01/01/2000` a `dd/mm/yyyy`

```sql
SELECT to_date('10/10/2020', 'dd/mm/yyyy') FROM DUAL;
```