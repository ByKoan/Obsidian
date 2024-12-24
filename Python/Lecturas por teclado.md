***Para leer valores por teclado en python tenemos la función `input()`***

```python
text = input("Introduze aqui tu texto:")
```

### Convertir datos ingresados:
- ***La función `input()` siempre devuelve un tipo string por lo que si queremos castear o cambiar el tipo de dato lo tendremos que poner de la siguiente forma:***

```python
edad = int(input("Ingrese aqui su edad:"))
print(edad)
```

### Leer mas de un valor:
- ***Si queremos leer mas de un valor tenemos mas de una forma para hacerlo:***
- ***Manera 1: "Separado por espacios:"***

```python
valores = input("Introduce varios números separados por espacios: ") numeros = valores.split() # Divide la cadena en una lista 
numeros = [int(num) for num in numeros] # Convierte cada elemento a entero 
print(f"Lista de números: {numeros}")
```

- ***Manera 2: "Utilizando un bucle:"***

```python
numeros = [] # Guardaremos los datos en este array
print("Introduce números uno a uno (escribe 'fin' para terminar):")
while True:
    valor = input("> ")
    if valor.lower() == "fin":
        break
    try:
        numeros.append(int(valor))
    except ValueError:
        print("Introduce un número válido.")
print(f"Lista de números: {numeros}")
```

### Manejos de Strings con métodos:
- ***Eliminar espacios al inicio y al final:*** 

```python
texto = input("Introduce un texto: ").strip()
```

- ***Convertir a mayúsculas o minúsculas:***

```python
texto = input("Introduce un texto: ").lower() 
texto = input("Introduce un texto: ").upper()
```
