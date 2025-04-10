PL/SQL Tiene variables como cualquier lenguaje de programación, con estas definiremos sus tipos de datos, almacenamiento de memoria etc...

Para ver los "Printf" de PL/SQL (Salidas o mensaje) usaremos la siguiente instrucción:

```sql
SET SERVEROUTPUT ON;
```

#### Declaración de variables:

- Siempre vamos a declarar las variables con una **v** antes de la variable indicando que es una variable
- Le podemos asignar valores a las variable desde el BEGIN mediante su nombre := valor

```sql
DECLARE
vVariable1 NUMBER;
vVariable2 NUMBER := 1;
-- Para iniciar la variable usaremos :=
vVariable3 NUMBER := '&cantidad';
-- Cuando queramos que el usuario nos introduzca un dato usamos al inicializar la variable el := '&"texto que queremos que aparezca"'
```

#### Salida de mensajes por pantalla:

- Como hemos indicado antes Oracle tiene salidas por pantalla y es gracias a sus funciones internas
- Sus funciones las vamos a llamar siempre con **DBMS**, y salida del mensaje la vamos a llamar asi:

```sql
DECLARE
	vNumero1 := 5;

BEGIN
	DBMS_OUTPUT.PUT_LINE('La variable 1 tiene el numero: '|| vNumero1);

END;
```