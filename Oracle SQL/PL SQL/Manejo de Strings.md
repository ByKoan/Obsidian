Oracle SQL maneja los Strings como cualquier otro lenguaje, aqui tenemos un par de programas de ejemplo para entenderlo mejor:

```sql
DECLARE
	vNombre VARCHAR2(20);
	vNombre2 VARCHAR2(20);
	vDireccion VARCHAR2(30);
	vEleccion VARCHAR2(1);

BEGIN 

	vNombre := 'Pedro Perez';
	vDireccion := 'Calle primero n1';
	vEleccion := 'y';

	IF (vEleccion = 'y') THEN
		DBMS_OUTPUT.PUT_LINE(vNombre);
		DBMS_OUTPUT.PUT_LINE(vDireccion);
	END IF;

-- Podemos usar funciones a la hora de imprimir para modificar la salida

	DBMS_OUTPUT.PUT_LINE(UPPER(vNombre)); -- Mayusculas
	DBMS_OUTPUT.PUT_LINE(LOWER(vNombre));  -- Minusculas
	DBMS_OUTPUT.PUT_LINE(INITCAP(vNombre)); -- Primera mayus
	DBMS_OUTPUT.PUT_LINE(SUBSTR(vNombre,1 ,1)); -- Extrae la primera 
	DBMS_OUTPUT.PUT_LINE(SUBSTR(vNombre,1 ,4)); -- Extrae las 4 primera 
	DBMS_OUTPUT.PUT_LINE(INSTR(vNombre, 'o')); -- Devuelve la posicion en la que se encuentra el caracter



	vNombre2 := '####Hello World!####';
	DBMS_OUTPUT.PUT_LINE(RTRIM(vNombre2, '#')); -- Elimina las almohadillas a la derecha
	DBMS_OUTPUT.PUT_LINE(LTRIM(vNombre2, '#')); -- Elimina las almohadillas a la izquierda
	DBMS_OUTPUT.PUT_LINE(TRIM('#' FROM vNombre2)); -- Elimina las almohadillas

END;
```

