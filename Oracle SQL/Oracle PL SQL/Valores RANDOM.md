Para obtener valores random en PL/SQL usamos la función `DBMS_RANDOM.VALUE`

```SQL
DECLARE
    v_num NUMBER;
BEGIN
    v_num := DBMS_RANDOM.VALUE(1, 100);
    DBMS_OUTPUT.PUT_LINE('Número aleatorio: ' || v_num);
END;
```
