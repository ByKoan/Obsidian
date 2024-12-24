***Estructuras de datos mutables que permiten almacenar pares de claves y valores. Muy útiles cuando necesitas asociar valores con claves únicas y realizar búsquedas rápidas ya que están basados en tablas de hash***


### Declaración de Diccionarios:

```python 
diccionario = {'clave1': 'valor1', 'clave2': 'valor2'} # Diccionario simple
diccionario = {} # Diccionario vacio
diccionario = dict(clave1='valor1', clave2='valor2') # Funcion dict()
diccionario = {1: 'uno', 2: 'dos', (1, 2): 'tupla'} # Diccionario con claves y valores de diferentes tipos
```

### Acceder a los elementos del diccionario:

- ***Acceso directo:***

```python
diccionario = {'nombre': 'Juan', 'edad': 30}
print(diccionario['nombre'])
print(diccionario['edad'])
```

- ***Manejo de claves que no existen:***

```python
print(diccionario.get('direccion', 'No encontrada'))
```

### Agregar y modificar elementos:

- ***Agregar elementos:***

```python
diccionario = {'nombre': 'Juan', 'edad': 30}
diccionario['direccion'] = 'Calle123'
print(diccionario)
```

- ***Modificar valores: Si la clave ya existe se modificara el elemento***

```python
diccionario['edad'] = 31
print(diccionario)
```

- ***Eliminar elementos:***

```python
del diccionario['direccion'] # Eliminar par clave-valor
valor = diccionario.pop('edad') # Elimina un par clave-valor y devuelve el valor
clave, valor = diccionario.popitem() # Elimina y devuelve el ultimo par clave-valor
diccionario.clear() # Elimina todos los pares clave-valor del diccionario 
```

### Métodos mas comunes en los diccionarios:

- ***Método `keys()`: devuelve una vista de todas las claves del diccionario***

```python
diccionario = {'nombre': 'Juan', 'edad': 30}
claves = diccionario.keys()
```

- ***Método `values()`: Devuelve una vista de todos los valores del diccionario***

```python
valores = diccionario.values()
```

- ***Método `items()`: devuelve una vista de todos los pares claves-valor como tuplas***

```python
items = diccionario.items()
```

- ***Método `get()`: Obtiene el valor asociado a una clave, si no existe devuelve un valor predeterminado***

```python
print(diccionario.get('edad', 'No encontrada'))
print(diccionario.get('direccion', 'No encontrada'))
```

- ***Método `update()`: Permite actualizar el diccionario con elementos de otro diccionario o de un iterable de pares clave-valor***

```python
diccionario.update({'direccion': 'Calle Real 456', 'telefono': '123456789'})
print(diccionario)  # Output: {'nombre': 'Juan', 'edad': 30, 'direccion': 'Calle Real 456', 'telefono': '123456789'}
```

### Recorrer un diccionario:

- ***Recorrer las claves de un diccionario:***

```python
diccionario = {'nombre': 'Juan', 'edad': 30}
for clave in diccionario:
    print(clave)
```

- ***Recorrer los valores de un diccionario:***

```python
for i in diccionario.values():
    print(i)
```

- ***Recorrer las 2 en un diccionario:***

```python
for clave, valor in diccionario.items():
    print(f"{clave}: {valor}")
```

### Estructuras mas complejas:

- ***Diccionarios con [[Listas (Arrays)|Arrays]]:***

```python
diccionario = {'nombre': 'Juan', 'hobbies': ['leer', 'deporte']}
print(diccionario['hobbies'])
```

- ***Diccionarios con otros diccionarios:***

```python
diccionario = {'persona': {'nombre': 'Juan', 'edad': 30}}
print(diccionario['persona']['nombre'])
```