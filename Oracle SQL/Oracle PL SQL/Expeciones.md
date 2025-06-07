Una expecion es un error que ocurre durante la ejecución de un bloque PL/SQL, te permite capturar y manejar estas situaciones.

```sql
BEGIN
    -- Código principal
EXCEPTION
    WHEN nombre_excepcion THEN
        -- Código para manejar el error
END;
```

Oracle ya tiene predefinidas ciertas excepciones:


| Excepcion               | Significado                                                                                                              |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| ACCES_INTO_NULL         | Se intenta asignar valores a un objeto que no se habia inicializado                                                      |
| CASE_NOT-FOUND          | Ninguna opción WHEN dentro de la instrucción CASE captura el valor y no hay instrucción ELSE                             |
| COLLECTION_IS_NULL      | Se intenta utilizar un varray o una tabla anidada que no estaba inicializada                                             |
| CURSOR_ALREADY_OPEN     | Se intenta abrir un cursor que ya se habia abierto                                                                       |
| DUP_VAL_ON_INDEX        | Se intento añadir una fila que provoca que un índice único repita valores                                                |
| INVALID_CURSOR          | Se realizo una operacion ilegal sobre un cursor                                                                          |
| INVALID_NUMBER          | Falla la conversion de caracter a numero                                                                                 |
| LOGIN_DEINED            | Se intenta conectar con Oracle usando un nombre de usuario/contraseña invalido                                           |
| NO_DATA_FOUND           | El select de fila unica no devolvio valores                                                                              |
| PROGRAM_ERROR           | Error interno de oracle                                                                                                  |
| ROWTYPE_MISMATCH        | Hay incompatibilidad de tipos entre el cursor y las variables a las que se intentan asignar sus valores                  |
| STORAGE_ERROR           | No hay memoria suficiente                                                                                                |
| SUBSCRIPT_BEYOND_COUNT  | Se hace referencia a un elemento de un varray o una tabla anidada usando un indice mayor que los elementos  que poseen   |
| SUBSCRIPT_OUTSIDE_LIMIT | Se hace referencia a un elemento de un varray o una tabla anidada usando un indice cuyo valor esta fuera del rango legal |
| SYS_INVALID_ROWID       | Se convierte un texto en un numero de identificacion de fila (ROWID) y el texto no valido                                |
| TIMEOUT_ON_RESOURCE     | Se consumio el maximo tiempo en el que Oracle permite esperar al recurso                                                 |
| TOO_MANY_ROWS           | El select de fila unica devuelve mas de una fila                                                                         |
| VALUE_ERROR             | Hay un error aritmetico de conversion de redondeo o de tamaño en una operacion                                           |
| ZERO_DIVIDE             | Se intento dividir entre 0                                                                                               |
### **Definición de nuestras propias EXCEPCIONES:**

```sql
DECLARE
    nombre_excepcion EXCEPTION;  -- 1. Declaración
BEGIN
    -- 2. Lógica de negocio
    IF condicion THEN
        RAISE nombre_excepcion;  -- 3. Lanzamiento
    END IF;

EXCEPTION
    WHEN nombre_excepcion THEN   -- 4. Captura
        -- Manejo del error
END;
```

### **RAISE_APLICATION_ERROR:**

```SQL
RAISE_APPLICATION_ERROR(número_error, mensaje, [mantener_stack]);
```

```SQL
BEGIN
    RAISE_APPLICATION_ERROR(-20001, 'Error de validación: el precio es negativo');
END;
```
### **Ejemplos:**

```sql
DECLARE 
	vSalario NUMBER;

BEGIN
	SELECT SALARIO INTO vSalario
	FROM EMPLEADO
	WHERE id = 999;
	DBMS_OUTPUT.PUT_LINE('Texto');

	EXCEPTION 
	 WHEN NO_DATA_FOUND THEN
	  DBMS_OUTPUT.PUT_LINE('Texto');

END;
```

```sql
DECLARE
    e_precio_negativo EXCEPTION;
    vPrecio NUMBER := -10;
BEGIN
    IF vPrecio < 0 THEN
        RAISE e_precio_negativo; -- Aqui lanzamos nuestra propia excepcion
    END IF;

    DBMS_OUTPUT.PUT_LINE('Precio válido: ' || vPrecio);

EXCEPTION
    WHEN e_precio_negativo THEN
        DBMS_OUTPUT.PUT_LINE('Error: El precio no puede ser negativo');
END;
```

