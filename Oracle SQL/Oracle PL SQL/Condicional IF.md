Como en cualquier otro lenguaje disponemos de los condicionales mas comunes, nos servirán para comprobar condiciones y ejecutar x código

### Condicional IF:

Estructura del condicional IF en Oracle SQL PL/SQL:

- Es importante no olvidarnos de la palabra clave `THEN` y el `END IF` para cerrar el condicional IF

```SQL
DECLARE 

	vVariableA NUMBER := 10;
	vVariableB NUMBER := 20;

BEGIN

	IF vVariableA > vVariableB THEN
	DBMS_OUTPUT.PUT_LINE(vVariableA ||'>'|| vVariableB);
	ELSE 
	DBMS_OUTPUT.PUT_LINE(vVariableA ||'<'|| vVariableB);
	END IF;

END;
```

```sql
DECLARE

	vNumero NUMBER := 100;

BEGIN

	IF (vNumero = 10) THEN
		DBMS_OUTPUT.PUT_LINE('Valor de numero es 10');
	ELSIF (vNumero = 20) THEN
		DBMS_OUTPUT.PUT_LINE('Valor de numero es 20');
	ELSE 
		DBMS_OUTPUT.PUT_LINE('Valor de numero es  > 20');

	END IF;

END;
```