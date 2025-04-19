Los procedimientos son "Funciones" (Bloques de código) destinado únicamente a ejecutar un código especifico, son compilados y posteriormente ejecutados:

Ejemplo:

```sql
CREATE OR REPLACE PROCEDURE hola 
AS
    BEGIN
        DBMS_OUTPUT.PUT_LINE('Hola a todos');
    END hola;

------------------------------------------------

    BEGIN 
        hola;
    END; -- Forma de ejecutar 1
    
    EXECUTE hola; -- Forma de ejecutar 2 
```

### Tipos de parámetros:

- Parámetros de entrada: Se usan para pasar información al procedimiento pero no se pueden cambiar dentro del procedimiento (Solo se leen)

```sql
CREATE OR REPLACE PROCEDURE saludar (
    nombre IN VARCHAR2
) IS
BEGIN
    DBMS_OUTPUT.PUT_LINE('Hola, ' || nombre);
END;
```

```sql
BEGIN
    saludar('Ana'); -- Metemos el dato cuando llamamos al procedimiento
END;
```

- Parámetros de salida: Se usan para devolver un valor desde el procedimiento hacia el que lo llama, el valor se asigna dentro del procedimiento:

```sql
CREATE OR REPLACE PROCEDURE obtener_doble (
    numero IN NUMBER,
    resultado OUT NUMBER
) IS
BEGIN
    resultado := numero * 2;
END;
```

```sql
DECLARE
    x NUMBER := 5;
    res NUMBER;
BEGIN
    obtener_doble(x, res);
    DBMS_OUTPUT.PUT_LINE('El doble es: ' || res);
END;
```

- Parámetros de Entrada/Salida: Son una mezcla de ambos, se pasa un valor al procedimiento y se puede modificar desde dentro 

```sql
CREATE OR REPLACE PROCEDURE incrementar (
    numero IN OUT NUMBER
) IS
BEGIN
    numero := numero + 1;
END;
```

```sql
DECLARE
    x NUMBER := 10;
BEGIN
    incrementar(x);
    DBMS_OUTPUT.PUT_LINE('El nuevo valor es: ' || x);
END;
```
