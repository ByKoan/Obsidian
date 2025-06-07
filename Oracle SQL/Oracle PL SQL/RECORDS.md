Son una estructura compuesta que permite agrupar varios campos ( de diferentes tipos) en una sola variable. 

```plsql
nombre_variable nombre_tabla%ROWTYPE;
```

```plsql
DECLARE
    v_empleado EMPLEADO%ROWTYPE;
BEGIN
    SELECT * INTO v_empleado
    FROM EMPLEADO
    WHERE id_empleado = 1;

    DBMS_OUTPUT.PUT_LINE(v_empleado.nombre || ' - ' || v_empleado.sueldo);
END;
```

```plsql
TYPE nombre_tipo IS RECORD (
    campo1 tipo1,
    campo2 tipo2,
    ...
);

nombre_variable nombre_tipo;
```

```sql
DECLARE
    TYPE LibroRec IS RECORD (
        titulo LIBRO.titulo%TYPE,
        precio LIBRO.precio%TYPE
    );

    v_libro LibroRec;
BEGIN
    SELECT titulo, precio INTO v_libro
    FROM LIBRO
    WHERE id_libro = 10;

    DBMS_OUTPUT.PUT_LINE('Título: ' || v_libro.titulo || ', Precio: ' || v_libro.precio);
END;
```