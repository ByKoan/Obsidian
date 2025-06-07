Una clave primaria va a ser un campo que identifique a esa tabla, no puede haber un campo igual en otra tabla.

```sql
CREATE TABLE nombreTabla (
campo1 varchar(20) NOT NULL,
campo2 number NOT NULL,
PRIMARY KEY(campo1)
);
```
