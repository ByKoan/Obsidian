Consiste en cruzar las tablas obteniendo todos los valores en común aunque no tengan relacion (Puedan ser NULL)

Se usan cuando:
- Cuando necesitas **todos los datos de la tabla principal** (izquierda), aunque no haya coincidencias en la tabla relacionada.

```sql
SELECT C.CAMPO1, C.CAMPO2, C.CAMPO3, P.CAMPO4
FROM TABLA
LEFT JOIN TABLA2
ON c.campo1 = p.campo4; -- Los campos del on tienen que tener los mismos valores
```
