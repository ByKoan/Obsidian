### Atributos:

- ***Atributos: variables asociadas a una clase o sus objetos***
- ***Atributos de clase: compartidos por todas las instancias de la clase***

```python
class Persona:
    especie = "Humano"  # Atributo de clase

print(Persona.especie)
```

- ***Atributos de instancia: únicos para cada objeto y se definen normalmente en el constructor***

```python
class Persona:
    def __init__(self, nombre):
        self.nombre = nombre  # Atributo de instancia

persona1 = Persona("Luis")
persona2 = Persona("Ana")
print(persona1.nombre)
print(persona2.nombre)
```

### Métodos:

- ***Métodos: Funciones definidas dentro de una clase que operan sobre los atributos***
- ***Métodos de instancia: trabajan con los datos del objeto, requieren el parámetro `self`***

```python
class Persona:
    def __init__(self, nombre):
        self.nombre = nombre

    def saludar(self):
        return f"Hola, soy {self.nombre}."

persona = Persona("Carlos")
print(persona.saludar())
```

- ***Métodos de clase: trabajan con atributos de clase y usan el decorador `@classmethod` su primer parámetro es `cls`***

```python
class Persona:
    especie = "Humano"

    @classmethod
    def cambiar_especie(cls, nueva_especie):
        cls.especie = nueva_especie
```

- ***Métodos estáticos: no dependen de ningún atributo de la clase o instancia. Usan el decorador `@staticmethod`***

```python
class Calculadora:
    @staticmethod
    def sumar(a, b):
        return a + b

print(Calculadora.sumar(3, 5))
```