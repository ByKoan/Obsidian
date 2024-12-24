***Las listas en Python son una de las estructuras de datos mas utilizadas, pueden contener cualquier tipo de datos incluso combinación de diferentes tipos:***

### Declaración de Arrays:

```python
array_vacio = []
array_enteros = [1, 2, 3, 4, 5]
array_mixto = [1, "Python", 3.14, True]
array_con_tupla = list((1, 2, 3)) # List() convierte una tupla en array
```

### Acceder a elementos:

- ***Pensemos que los arrays son como una lista en la que tu tienes diferentes elementos con un numero por posición es decir en la posición 1 tienes x valor, en la 2 tienes y etc...*** 

- ***Para acceder a estos elementos se usan los corchetes igual que para declararlos pero poniendo la posición a la que queremos acceder (Siempre se empieza desde la posición 0):***

```python
mi_array = [10, 20, 30, 40, 50]

# Acceder a un elemento por su índice
print(mi_array[0])  # 10
print(mi_array[3])  # 40

# Acceso inverso (índices negativos)
print(mi_array[-1])  # 50
print(mi_array[-2])  # 40
```

### Modificar elementos:

- ***Los arrays son "MUTABLES" por lo que puedes cambiar el valor de sus elementos cuando quieras:***

```python
mi_lista = [10, 20, 30]
mi_lista[1] = 25  # Cambia el segundo elemento
print(mi_lista)  # [10, 25, 30]
```

### Recorrer un Array:

- ***Recorrer un array es fácil, usaremos un bucle FOR para ello:*** 

```python
array = ["a", "b", "c"]

for i in array:
	print(i)
```

- ***Si queremos recorrer un array con índices lo haremos de la siguiente forma:***

```python
array = ["a", "b", "c"]

for i in range(len(array)):
    print(f"Elemento {i}: {mi_lista[i]}")
```

### Comprensión de arrays (Array Comprehension):

- ***Forma concisa de crear Arrays:***

```python
# Crear una lista de cuadrados de los números del 1 al 5
cuadrados = [x**2 for x in range(1, 6)]  # [1, 4, 9, 16, 25]

# Filtrar valores
pares = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
```

### Operaciones comunes con Arrays:

- ***Concatenar listas:***
```python
array1 = [1, 2]
array2 = [2, 4]
array3 = array1 + array2
```

- ***Repetir Listas:***
```python
array = [1, 2]
array_repetido = array * 3 # [1, 2, 1, 2, 1, 2]
```

- ***Verificar elementos:***
```python
print(3 in [1, 2, 3])
```

### Métodos mas comunes con Arrays:

| Metodo                  | Descripcion                                                              |
| ----------------------- | ------------------------------------------------------------------------ |
| `append(elemento)`      | Agrega un elemento al final del array                                    |
| `extend(otroarray)`     | Agrega los elementos de otro array                                       |
| `ìnsert(indice, valor)` | Inserta un valor en una posicion especifica                              |
| `remove(valor)`         | Elimina la primera aparición de un valor especifico                      |
| `pop(indice)`           | Elimina y devuelve el elemento en el índice dado (por defecto el ultimo) |
| `clear()`               | Elimina todos los valores del array                                      |
| `index(valor)`          | Devuelve el índice de la primera aparición del valor dado                |
| `count(valor)`          | Devuelve el numero de veces que un valor aparece en la lista             |
| `sort()`                | Ordena la lista en su lugar                                              |
| `reverse()`             | Invierte el orden de los elementos en la lista                           |
| `copy()`                | Devuelve una copia superficial de la lista                               |
- ***Ejemplos:***

```python
mi_array = [1, 2, 3]
mi_array.append(4)  # [1, 2, 3, 4]
mi_array.insert(1, 10)  # [1, 10, 2, 3, 4]
mi_array.remove(10)  # [1, 2, 3, 4]
ultimo = mi_array.pop()  # Elimina y devuelve el último elemento (4)
```

### Longitud y otras funciones útiles:

- ***Obtener longitud del array:***

```python
print(len([1, 2, 3]))
```

- ***Obtener máximo y mínimo del array:***

```python
print(max([1, 2, 3]))
print(min([1, 2, 3]))
```

- ***Sumar elementos:***

```python
print(sum([1, 2, 3]))
```

### Arrays Anidados:

- ***Los arrays se pueden componer a su vez por mas arrays (Matriz):***

```python
matriz = [[1, 2], [3, 4], [5, 6]]

print(matriz[1][0]) #Primer corchete array al que acceder segundo posicion

```