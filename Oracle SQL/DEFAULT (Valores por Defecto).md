Palabra clave `DEFAULT` 

```SQL
CREATE TABLE nombreTabla (
campo1 varchar(20) NOT NULL,
campo2 varchar(30) DEFAULT 'Desconocido',
campo3 number DEFAULT 0
);
```

```sql
INSERT INTO nombreTabla VALUES('Valor', DEFAULT, DEFAULT);
```
