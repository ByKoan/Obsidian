Los trigger o disparadores son bloques de códigos que se "disparan" automáticamente ósea se ejecutan automáticamente cuando ocurre un evento especifico, como un INSERT, UPDATE O DELETE sobre una tabla, un DDL (CREATE o ALTER) o un evento del sistema (STARTUP o LOGON).

A diferencia de procedimientos almacenados los trigger no se invocan explícitamente por lo cual no hace falta llamarlos en ningún lado, simplemente permanecen habilitados o deshabilitado y el motor de Oracle los ejecuta cuando se da la condición configurada

Como norma general haremos un solo trigger por tabla ya que si creamos vario no garantiza q vayan a saltar todos, entonces lo mejor es juntar toda la lógica en uno y que se ejecuten las excepciones necesarias

### Tipos de Triggers:

#### Según momento de ejecución:

- **BEFORE** : Se ejecutan antes de que la operación modifique la tabla, útiles para validar o modificar datos de entrada.
- **AFTER** : Se ejecutan tras la operación, idóneos para auditoria o acciones dependientes de cambios confirmados
- **INSTEAD OF** : Solo para vistas, remplazan la operación DML y permiten actualizar vistas complejas

#### Según el nivel:

- **STATEMENT-LEVEL** : Un único disparo por sentencia, independientemente de cuantas filas afecte
- **ROW-LEVEL (FOR EACH ROW)** : Se dispara una vez por cada fila modificada; se permite usar `:NEW` y `:OLD` para acceder a valores fila a fila 

#### Triggers del sistema:

- Se disparan ante eventos globales como logon, logoff, startup o shutdown de la base de datos

#### Pseudoregistros :NEW y :OLD:

- En los triggers de fila, Oracle proporciona dos Pseudoregistros
	- **:OLD** Valores antes de la operación (Solo UPDATE y DELETE)
	- **:NEW** Valores después de la operación (solo INSERT y UPDATE) Sirven para validaciones, auditorias o para derivar otros valores

### Sintaxis básica de un Trigger:

```sql
CREATE [OR REPLACE] TRIGGER nombre_trigger
-- Creacion del trigger
  {BEFORE | AFTER | INSTEAD OF}
-- Cuando se ejecutara
  {INSERT [OR] | UPDATE [OF columna_list] [OR] | DELETE}
-- Como se ejecutara (Al actualizar, insertar o eliminar)
  ON objeto (tabla o vista)
-- En que campo (Objeto) de que tabla o vista
  [REFERENCING OLD AS o NEW AS n]
-- Uso de pseudoelementos
  [FOR EACH ROW]
-- Uso de auto ejecucion en cada fila modificada
  [WHEN (condición_plsql)]
-- Condicion que tendra el trigger
DECLARE
  -- sección de declaraciones opcional
BEGIN
  -- acciones del trigger
EXCEPTION
  -- manejador de excepciones opcional
END;
```

### Ejemplos prácticos:

```sql
CREATE OR REPLACE TRIGGER trg_audit_employees
-- Creacion del trigger
AFTER INSERT OR UPDATE OR DELETE ON employees
-- Despues de insertar o actualizar o eliminar valores en empleados
FOR EACH ROW
-- Se ejecutara en cada fila modificada
BEGIN
  -- Lo que ejecutara el trigger
  INSERT INTO audit_employees(emp_id, action, action_date)
  VALUES(NVL(:OLD.employee_id, :NEW.employee_id),
         CASE
           WHEN INSERTING THEN 'INSERT'
           WHEN UPDATING THEN 'UPDATE'
           WHEN DELETING THEN 'DELETE'
         END,
         SYSDATE);
END;
```

```sql
CREATE OR REPLACE TRIGGER trg_check_salary
-- Creacion del trigger
BEFORE INSERT OR UPDATE OF salary ON employees
-- Antes de insertar o actualizar salarios en empleados
FOR EACH ROW
-- Actualize en cada fila
WHEN (NEW.salary < 0 OR NEW.salary > 100000)
-- Condicion
BEGIN
  -- Codigo que ejecutara el trigger
  RAISE_APPLICATION_ERROR(-20001, 'Salario fuera de rango permitido');
END;
```

```sql
CREATE OR REPLACE TRIGGER trg_empleado_actualizado
BEFORE UPDATE OF salario, puesto ON empleados
FOR EACH ROW
WHEN (:OLD.salario != :NEW.salario OR :OLD.puesto != :NEW.puesto)
BEGIN
   INSERT INTO cambios_empleados (id_empleado, descripcion_cambio, fecha_cambio)
   VALUES (:OLD.id_empleado, 'Cambio en salario o puesto', SYSDATE);
END;
```