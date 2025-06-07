Hay varias formas, Primera metiendo todos los valores de la tabla:

```sql
INSERT INTO tabla VALUES (valor1, valor2...);
```

Segunda, metiendo solo los valores que queramos:

```sql
INSERT INTO tabla (campo1, campo2, campo3...) 
VALUES (valor1, valor2, valor3...);
```

Tercera insertando múltiples registros

```sql
INSERT ALL
	INTO tabla (campo1, campo2, campo3...) VALUES (valor1, valor2, valor3...);
	INTO tabla (campo1, campo2, campo3...) VALUES (valor1, valor2, valor3...);
```

Cuarta insertando desde otra tabla:

```SQL
INSERT INTO tabla (campo1, campo2, campo3...)
SELECT campo1, campo2, campo3
FROM tabla
WHERE campo > condicion;
```
