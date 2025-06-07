En Oracle SQL tenemos varios tipos de bucles en los que mediante una condición se va a repetir una secuencia de código

### Bucle LOOP:

El bucle LOOP es el mas básico de todos, en el siguiente programa contamos con una variable inicial con valor 10, y lo que hacemos con el bucle es ir sumándola 10 hasta que el IF dentro del bucle cuenta que es mayor de 50 y sale.

```SQL
DECLARE

	vValor number := 10;
	
BEGIN

	LOOP
		DBMS_OUTPUT.PUT_LINE(vValor);
		vValor:= vValor + 10;
		IF vValor > 50 THEN
		EXIT;
		END IF;
	END LOOP;

	DBMS_OUTPUT.PUT_LINE('Valor final =' || vValor);	

END;
```

### Bucle WHILE:

El bucle WHILE consiste en que hasta que la condición no se cumpla se vaya iterando: 

```sql
DECLARE 
	vValor NUMBER := 10;

BEGIN

	WHILE vValor < 20 LOOP
		DBMS_OUTPUT.PUT_LINE('El valor es: ' || vValor);
		vValor := vValor + 1;
	END LOOP;

END;
```

### Bucle FOR:

El bucle FOR es bastante parecido al bucle WHILE

```SQL
DECLARE 

	vNumero NUMBER;

BEGIN 
	FOR vNumero IN 10..20 LOOP
		DBMS_OUTPUT.PUT_LINE('Valor del numero: ' || vNumero);
	END LOOP;

END;
```

Podemos hacer bucles FOR inversos

```sql
DECLARE 

	vNumero NUMBER;

BEGIN 
	FOR vNumero IN REVERSE 10..20 LOOP
		DBMS_OUTPUT.PUT_LINE('Valor del numero: ' || vNumero);
	END LOOP;

END;
```