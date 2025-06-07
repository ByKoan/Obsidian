Como en cualquier otro lenguaje, Oracle tiene variables constantes

```sql
DECLARE

	vMensaje CONSTANT VARCHAR2(30) := 'Hello World';

BEGIN 

	DBMS_OUTPUT.PUT_LINE('La variable contiene el texto: ' || vMensaje);

END;
```
