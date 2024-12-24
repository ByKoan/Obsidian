***Los condicionales de python se componen por el clásico if-else-elif, condicionales lógicos y condicionales de comparación:***

### Condicional IF:

- ***Condicional mas conocido:***

```python
if condición:
    # Código a ejecutar si la condición es verdadera
```

- ***IF + ELSE (Si no se da la condición que se de el ese):***

```python
if condición:
    # Código si la condición es verdadera
else:
    # Código si la condición es falsa
```

- ***IF + ELIF + ELSE (Si no se da la primera condición se puede dar otra/s si no se da el else):***

```python
if condición1:
    # Código si condición1 es verdadera
elif condición2:
    # Código si condición2 es verdadera
    # Podemos añadir tantos elif como necesitemos
else:
    # Código si ninguna condición es verdadera
```

### Condicionales Lógicos:

- ***Puedes combinar condiciones con los siguientes operadores lógicos: `and`, `or` y `not`***

```python
x = 10
y = 20

if x > 5 and y > 15:
    print("Ambas condiciones son verdaderas.")
elif x > 15 or y > 15:
    print("Al menos una condición es verdadera.")
else:
    print("Ninguna condición es verdadera.")
```

### Operadores de Comparación:

- ***Existen los siguientes: `==` igualdad, `!=` diferente a y `<`, `>`, `<=` y `>=` comparaciones.***

```python
a = 5
b = 10

if a != b:
    print("a y b son diferentes.")
```

### Declaración PASS en condicionales:

- ***La palabra clave `pass` se utiliza para crear un bloque vacío. Se usar para evitar errores de sintaxis.***

```python
if True:
    pass
```

### Tipos de valores en condicionales:

- ***Verdaderos números distintos a 0, strings no vacíos, arrays no vacíos etc...***
- ***Falso `none`, `0`, strings vacíos, (`""`), arrays vacíos (`[]`), etc...***

```python
if []:  # Una lista vacía es Falsa.
    print("Esto no se imprimirá.")
else:
    print("Lista vacía evaluada como Falsa.")
```