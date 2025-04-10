### Función `chr`:

- Devuelve el carácter que coincida con la posición que le demos en ASCII

```SQL
SELECT CHR(65) FROM DUAL;
-- -> Retorna 'A'
-- DUAL Es una tabla del sistema donde podemos realizar operaciones
```

### Función `ascii`:

- El contrario que la función `chr`, nos devuelve el numero con el que coincida la letra en ASCII

```SQL
SELECT ASCII('A') FROM DUAL;
-- -> Retorna 65
```

### Función `initcap`:

- Pone la primera letra a mayúscula

```sql
SELECT INITCAP('hello world') FROM DUAL;
```

### Función `lower`:

- Pone todas las letras a minúscula

```sql
SELECT LOWER('HELLO WORLD') FROM DUAL;
```

### Función `upper`:

- Pone todas las letras a mayúscula

```sql
SELECT UPPER('hello world') FROM DUAL;
```

### Función ``lpad``:

- Indicas cuantos caracteres tiene que ocupar un STRING y esta función lo rellena con texto indicado a la izquierda

```sql
SELECT LPAD('oracle',11,'abc') FROM DUAL;
-- Retorna -> 'abcaboracle'
```

### Función `rpad`:

- Lo mismo que `lpad` pero a la derecha

```sql
SELECT RPAD('oracle',9,'abc') FROM DUAL;
-- Retorna 'oracleabc'
```

### Funcion `substr`:

- Nos devuelve un substring del string especificado:

```sql
SELECT SUBSTR(EMAALU,1,INSTR(EMAALU, '@') -1)
FROM ALUMNO;
```