***Comentarios de una sola linea en Python:***

```python
# Esto es un comentario de una sola linea
```

***Comentarios de varias líneas con docstring:***

- Para una función:

```python
def suma(a, b):
    """
    Suma dos números y retorna el resultado.
    
    Parámetros:
        a (int): Primer número.
        b (int): Segundo número.
    
    Retorna:
        int: La suma de los dos números.
    """
    return a + b

print(suma.__doc__) # Imprime el docstring 
```

- Para una clase:

```python
class Persona:
    """
    Representa a una persona con nombre y edad.

    Métodos:
        saludar(): Imprime un saludo.
    """
    
    def __init__(self, nombre, edad):
        """
        Inicializa una nueva instancia de Persona.

        Parámetros:
            nombre (str): El nombre de la persona.
            edad (int): La edad de la persona.
        """
        self.nombre = nombre
        self.edad = edad

print(Persona.__doc__)
```

- Para un modulo:

```python
"""
Este módulo contiene funciones para realizar operaciones básicas.

Funciones:
    suma(a, b): Retorna la suma de dos números.
    resta(a, b): Retorna la resta de dos números.
"""

print(__doc__)
```