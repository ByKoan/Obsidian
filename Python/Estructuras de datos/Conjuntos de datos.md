***Estructuras de datos que permiten almacenar colecciones de elementos únicos y desordenados. Muy útiles cuando necesitas asegurar que no haya elementos duplicados o necesites realizar operaciones matemáticas de teoría de conjuntos como unión, intersección o diferencia***

### Declaración de los Conjuntos de Datos:

```python
conjunto = set([1, 2, 3, 4]) # funcion set()
conjunto = {1, 2, 3, 4} # Usando llaves
cojunto = set() # Conjunto vacio
conjunto = set("Hola") # Crea un conjunto de caracteres unicos en los que la salida sera {'H', 'o', 'l', 'a'}
```

### Operaciones con Conjuntos:

- ***Agregación de elementos:***

```python
conjunto = {1, 2, 3}
conjunto.add(4)
print(conjunto) # {1, 2, 3, 4}
```

- ***Eliminar elementos:***

```python
conjunto = {1, 2, 3}
conjunto.remove(2)
print(conjunto) # {1, 3}
```

- ***Eliminar un elemento, si no existe no manda ningún error:***

```python
conjunto = {1, 2, 3}
conjunto.discard(4)
print(conjunto) # {1, 2, 3}
```

- ***Eliminar y retornar un elemento aleatorio del conjunto:***

```python
conjunto = {1, 2, 3}
print(conjunto.pop)
```

- ***Verificar si el valor esta en el conjunto de datos:***

```python
conjunto = {1, 2, 3}
print(2 in conjunto)
```

### Operaciones de teoría de conjuntos:

- ***Operación de unión:***

```python
conjunto1 = {1, 2, 3}
conjunto2 = {3, 4, 5}
union = conjunto1 | conjunto2
print(union) # {1, 2, 3, 4, 5}
```

- ***Operación de intersección:***

```python
conjunto1 = {1, 2, 3}
conjunto2 = {3, 4, 5}
interseccion = conjunto1 & conjunto2
print(interseccion)
```

- ***Operación de diferencia:***

```python
conjunto1 = {1, 2, 3}
conjunto2 = {3, 4, 5}
diferencia = conjunto1 - conjunto2
print(diferencia)
```

- ***Diferencia simétrica:***

```python
conjunto1 = {1, 2, 3}
conjunto2 = {3, 4, 5}
dif_simetrica = conjunto1 ^ conjunto2
print(dif_simetrica)
```

### Subconjuntos y Superconjuntos

- ***Un subconjunto es un conjunto de otro si todos sus elementos están en el otro conjunto:***

```python
conjunto1 = {1, 2}
conjunto2 = {1, 2}
print(conjunto1.isdisjoint(conjunto2))
```

- ***Un superconjunto es un conjunto de otro si contiene todos los elementos del otro conjunto:***

```python
conjunto1 = {1, 2, 3}
conjunto2 = {1, 2}
print(conjunto1.issuperset(conjunto2))
```

### Conversión entre tipos:

- ***De array a conjunto:***

```python
array = [1, 2, 2, 3, 4]
conjunto = set(lista)
print(conjunto)
```

- ***De conjunto a array:***

```python
conjunto = {1, 2, 3, 4, 5}
array = list(conjunto)
print(array)
```
