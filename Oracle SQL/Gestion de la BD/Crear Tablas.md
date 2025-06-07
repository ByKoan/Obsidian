```sql
CREATE TABLE nombreTabla(
campo1 tipoCampo,
campo2 tipoCampo
);
```

```sql
CREATE TABLE empleados (
    empleado_id NUMBER PRIMARY KEY,
    nombre      VARCHAR2(100) NOT NULL,
    puesto      VARCHAR2(50),
    salario     NUMBER(8,2),
    fecha_ingreso DATE DEFAULT SYSDATE
);
```

