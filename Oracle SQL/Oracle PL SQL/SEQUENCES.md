Las secuencias son ciclos que se van repitiendo cada vez que indicamos el siguiente paso, normalmente usadas para poner IDs automáticamente

```sql
CREATE SEQUENCE secuencia
START WITH 1 
INCREMENT BY 1
MAXVALUE 9999
MINVALUE 1
CYCLE;
```

Así insertamos datos con una secuencia:

```sql
INSERT INTO TABLA VALUES(
secuencia.nextval,
'Valor2',
'Valor3'...
);
```

Para reiniciar/borrar una secuencia usamos:

```sql
DROP SEQUENCE secuencia;
```