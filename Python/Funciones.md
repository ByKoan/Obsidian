***Bloques de código reutilizables de una tarea especifica, normalmente usadas para que el código sea mas legible con bloques de código que se tendrán que repetir mas de una vez***

### Declarar Funciones:

```python
def nombre_funcion(argumento1, argumento2):
	# Codigo...
	return valor # Opcional, solo si hace falta retornar/devolver algo
```

- ***Ejemplo:***

```python
def sumar(a, b):
    return a + b

resultado = sumar(3, 5)
print(resultado)
```

### Llamadas a función:

- ***Para ejecutar una función basta con llamarla usando su nombre seguido de un paréntesis con los argumentos:***

```python
nombre_funcion(arg1, arg2)
```

### Parámetros por defecto:

```python
def saludar(nombre, mensaje="Hola"):
    print(f"{mensaje}, {nombre}!")

saludar("Carlos")
saludar("Carlos", "Buenos días")
```


### Tipos de Variables en Funciones:

- ***Existen dos tipos de variables teniendo en cuenta las funciones, locales y globales. Las locales solo existen dentro de la función y las globales se puede acceder a ellas desde cualquier parte del código***

```python
x = 10  # Variable global

def funcion():
    y = 5  # Variable local
    print(x + y)

funcion()
```

### Funciones anónimas (Lambdas):

- ***Funciones pequeñas de una sola lineal definidas con la palabra clave `lambda`***

```python
doble = lambda x: x * 2
print(doble(5))
```

### Funciones de orden superior:

- ***Funciones que aceptan otras funciones como argumentos o las devuelven como resultado:***

```python
numeros = [1, 2, 3]
cuadrados = list(map(lambda x: x**2, numeros))
print(cuadrados)
```

### Decoradores:

- ***Funciones que modifican el comportamiento de otras funciones:*** 

```python
def decorador(func):
    def envoltura():
        print("Antes de la función")
        func()
        print("Después de la función")
    return envoltura

@decorador
def saludo():
    print("Hola!")

saludo()
```

### Recursividad:

- ***Una función puede llamarse a si misma:***

```python
def factorial(n):
    if n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))
```

### Documentación de Funciones:

- ***Python cuenta con `docstring` para escribir lo que hace la función (Forma muy útil de documentar sobre el mismo código):***

```python
def sumar(a, b):
    """Devuelve la suma de dos números."""
    return a + b

print(sumar.__doc__)
```