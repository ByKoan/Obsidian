Como en cualquier otro lenguaje disponemos de los condicionales mas comunes, nos servirán para comprobar condiciones y ejecutar x código

### Condicional CASE:

```sql
CASE[expresion]
	WHEN valor1 condicion then
		codigo
	WHEN valor2 condicion then
		codigo
	ELSE 
		codigo
END CASE;
```

```SQL
DECLARE 
	vNumLibros NUMBER;
	vNumBarato NUMBER;
	vNumCaro NUMBER;
	vPrecio NUMBER := &VALOR;

BEGIN
	SELECT COUNT(*) INTO vNumLibros
	FROM LIBRO;

	SELECT COUNT(*) INTO vNumCaro
	FROM LIBRO
	WHERE precio > vPrecio;
	vNumBarato := vNumLibros - vNumCaro;

	CASE
		WHEN vNumBarato > 5 THEN
			DBMS_OUTPUT.PUT_LINE('Texto');
		WHEN vNumBarato > 3 THEN
			DBMS_OUTPUT.PUT_LINE('Texto');
		ELSE
			DBMS_OUTPUT.PUT_LINE('Texto');
	END CASE;
END;
```