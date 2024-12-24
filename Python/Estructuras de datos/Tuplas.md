***Estructura de datos que nos permite almacenar una colección ordenada de elementos. Similar a los arrays pero con la diferencia de que son inmutables lo que significa que no se puede modificar una vez creadas***

### Declaración de tuplas:

```python
tupla = {1, 2, 3, 'a', 'b'}
tupla = 1, 2, 3, 'a', 'b' # Empaquetado de tupla
tupla = (5,) # Un solo elemento (Necesaria la coma del final)
tupla = ()

array = [1, 2, 3]
tupla = tuple(array) # De array a tupla
```

### Acceso a los elementos:

```python
tupla = (10, 20, 30, 40)
print(tupla[0])
print(tupla[-1])
```

### Operaciones comunes con tuplas:

- ***Concatenación:***

```python
tupla1 = (1, 2)
tupla2 = (3, 4)
resultado = tupla1 + tupla2
```

- ***Repetición:***

```python
tupla = (1, 2)
print(tupla * 3)
```

- ***Comprobar si un elemento esta en una tupla:***

```python
tupla = (1, 2, 3)
print(2 in tupla)
```

- ***Recorrer una tupla:***

```python
tupla = (1, 2, 3)

for i in tupla:
	print i
```

### Desempaquetado de tuplas:

- ***Puedes asignar los elementos de una tupla a variables individuales:***

```python
tupla = (10, 20, 30)
a, b, c = tupla
print(a, b, c)
```