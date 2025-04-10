***Define la estructura y el comportamiento de un conjunto de objetos. Contiene atributos (Datos) y métodos (funciones que operan sobre los datos):***

### Declaración de Clases:

```python
class MiClase:
    atributo = "Valor por defecto"
```

### Crear Objetos (Instancias):

- ***Un objeto se crea llamando a la clase como si fuera una función:***

```python
mi_objeto = MiClase()
print(mi_objeto.atributo)
```

### Método Constructor ( `__init__` ):

- ***El método especial `__init__` es el constructor de la clase. Se ejecuta automáticamente al crear un objeto y se usa para inicializar atributos de instancia***

```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre  # Atributo de instancia
        self.edad = edad

persona = Persona("Ana", 25)
print(persona.nombre)  # Salida: Ana
print(persona.edad)    # Salida: 25
```