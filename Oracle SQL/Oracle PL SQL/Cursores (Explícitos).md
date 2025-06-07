Se usan cuando necesitamos que el programa nos devuelva mas de un registro

### Atributos de cursores:

`%ISOPEN` Devuelve "True" si el cursor esta abierto
`%FOUND` Devuelve "True" si el registro fue satisfactoriamente procesado
`%NOTFOUND` Devuelve "True" si el registro no pudo ser procesado
`%ROWCOUNT` Devuelve el numero de registros que han sido procesados hasta ese momento

## **Cursores con bucles:**
### Cursores en LOOP:

```SQL
DECLARE
    CURSOR c_libros IS
        SELECT id_libro, titulo, precio FROM LIBRO;

    v_id LIBRO.id_libro%TYPE;
    v_titulo LIBRO.titulo%TYPE;
    v_precio LIBRO.precio%TYPE;
BEGIN
    OPEN c_libros;
    LOOP
        FETCH c_libros INTO v_id, v_titulo, v_precio;
        EXIT WHEN c_libros%NOTFOUND;
        DBMS_OUTPUT.PUT_LINE('ID: ' || v_id || ', Título: ' || v_titulo || ', Precio: ' || v_precio);
    END LOOP;
    CLOSE c_libros;
END;
```

### Cursores con WHILE LOOP:

```sql
DECLARE
    CURSOR c_libros IS
        SELECT id_libro, titulo, precio FROM LIBRO;

    v_id LIBRO.id_libro%TYPE;
    v_titulo LIBRO.titulo%TYPE;
    v_precio LIBRO.precio%TYPE;
BEGIN
    OPEN c_libros;
    FETCH c_libros INTO v_id, v_titulo, v_precio;

    WHILE c_libros%FOUND LOOP
        DBMS_OUTPUT.PUT_LINE('ID: ' || v_id || ', Título: ' || v_titulo || ', Precio: ' || v_precio);
        FETCH c_libros INTO v_id, v_titulo, v_precio;
    END LOOP;

    CLOSE c_libros;
END;
```

### Cursores con FOR LOOP:

```SQL
DECLARE
    CURSOR c_libros IS
        SELECT id_libro, titulo, precio FROM LIBRO;
BEGIN
    FOR libro IN c_libros LOOP
        DBMS_OUTPUT.PUT_LINE('ID: ' || libro.id_libro || ', Título: ' || libro.titulo || ', Precio: ' || libro.precio);
    END LOOP;
END;
```

## **Ejemplos de cursores:**
### Ejemplo básico de Cursor Explicito:

- Los cursores explícitos o multiregistros literalmente hacen una consulta multiregistro y la guardan en variables previamente declaradas mediante el `FETCH`

```sql
SET SERVEROUTPUT ON;

DECLARE
    -- Variables en la que guardaremos los datos del programa
    v_docu empleados.documento%TYPE;
    v_nom empleados.nombre%TYPE;
    v_ape empleados.apellido%TYPE;
    v_suel empleados.sueldo%TYPE;
    
    -- Cursor donde declararemos la consulta que obtendra el multiregistro
    CURSOR C_CURSOR2 IS 
        select documento, nombre, apellido, sueldo
        from empleados
        where documento=22222222;

BEGIN
    
    OPEN C_CURSOR2; -- Abrimos el cursor
    FETCH C_CURSOR2 INTO v_docu, v_nom, v_ape, v_suel; -- Guardamos los datos en las variables
    close C_CURSOR2; -- Cerramos cursor 
    DBMS_OUTPUT.PUT_LINE('Documento: '|| v_docu);
    DBMS_OUTPUT.PUT_LINE('Nombre: '|| v_nom);
    DBMS_OUTPUT.PUT_LINE('Apellidos: '|| v_ape);
    DBMS_OUTPUT.PUT_LINE('Sueldo: '|| v_suel);

END;
```

### Ejemplo básico Cursor SELECT y UPDATE:

```sql
SET SERVEROUTPUT ON;

DECLARE
    v_empleados empleados%rowtype;

BEGIN 
    FOR v_empleados in (SELECT * FROM EMPLEADOS) LOOP
    DBMS_OUTPUT.PUT_LINE(v_empleados.sueldo);
    -- Mediante estas lineas seleccionaremos todos los sueldos existentes de la tabla
    END LOOP;
END;

--------------------------------------------------

BEGIN

    UPDATE empleados SET sueldo = 10000
    WHERE documento = '0000000';
    -- Mediante estas lineas actualizaremos el registro del campo especificado
    IF SQL%NOTFOUND THEN
        DBMS_OUTPUT.PUT_LINE('No existe registro para modificar');
    END IF;

END;
```

### Ejemplo básico Cursor con parámetros:

```sql
SET SERVEROUTPUT ON;

DECLARE

    v_nom productos.nombre_producto%TYPE; 
    v_pre productos.precio%TYPE;
    
    CURSOR C_PRODUCTOS ( idprod productos.id_producto%TYPE ) 
    -- Declaramos que le vamos a pasar por parametros al abrirle en el begin el campo id 
    -- Para que al devolver los registros solo nos devuelva los que tengan que ver con la ID especificada
        IS
        SELECT nombre_producto, precio from productos
        where id_producto = idprod;

BEGIN

    OPEN C_PRODUCTOS(3);
    LOOP
        FETCH c_productos into v_nom, v_pre;
        exit when c_productos%notfound;
        DBMS_OUTPUT.PUT_LINE('Articulo: ' || v_nom || ', precio: ' || v_pre);
    END LOOP;
    CLOSE C_PRODUCTOS;
    
END;
```
