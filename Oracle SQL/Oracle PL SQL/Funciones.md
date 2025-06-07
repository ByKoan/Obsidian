Bloques de código que realizan una única operación y devuelven un dato:

#### Estructura básica:

```sql
CREATE OR REPLACE FUNCTION nombre_funcion (
   parametro1 [modo] tipo_dato,
   parametro2 [modo] tipo_dato
)
RETURN tipo_dato_retorno
IS
   -- Variables locales
BEGIN
   -- Lógica
   RETURN valor;
END nombre_funcion;
```

Los parámetros siguen la misma lógica que los de los procedimientos, es decir:
- Entrada: Solo se modifican al principio del programa
- Salida: Se modifican durante el programa
- Entrada/salida: Es una mezcla

### Ejemplo básico:

```sql
CREATE OR REPLACE FUNCTION obtener_area_circulo (
   radio IN NUMBER
)
RETURN NUMBER
IS
   area NUMBER;
BEGIN
   area := 3.1416 * radio * radio;
   RETURN area;
END;
```

```sql
BEGIN
   DBMS_OUTPUT.PUT_LINE(obtener_area_circulo(5));
END;
```
