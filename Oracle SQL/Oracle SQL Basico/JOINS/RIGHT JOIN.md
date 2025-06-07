Consiste en cruzar las tablas obteniendo todos los valores en común aunque no tengan relacion (Puedan ser NULL)

Se usan cuando:
- Cuando necesitas **todos los datos de la tabla principal** (derecha), aunque no haya coincidencias en la tabla relacionada.

```sql
SELECT C.CAMPO1, C.CAMPO2, C.CAMPO3, P.CAMPO4
FROM TABLA C
RIGHT JOIN TABLA2 P
ON C.CAMPO1 = P.CAMPO4;
```