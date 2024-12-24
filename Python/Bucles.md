***En python al igual que en C tenemos los bucles mas comunes entre ellos el FOR y el WHILE*** 

### Bucle FOR en Python:

- Normalmente usado para recorrer un rango con una determinada condición: 

```python
for i in range(0, 10): # Recorremos desde el 0 hasta el 10
    print(i)
```

### Bucle WHILE en Python:

- Normalmente utilizado como el bucle **FOR** pero podemos hacer también bucles infinitos

```python
contador = 5  # Inicializamos una variable

while contador > 0:  # El bucle continuará mientras el contador sea mayor que 0
    print(f"El contador es: {contador}")
    contador -= 1  # Reducimos el valor del contador en cada iteración

print("¡El bucle ha terminado!")

```

- ***Bucle WHILE infinito:***

```python
while True:  # True siempre es verdadero
    print("Bucle infinito. Presiona Ctrl+C para salir.")
```

### Alternativa al bucle DO-WHILE en Python:

```python
condition = False
while True:
    print("Este código se ejecuta al menos una vez.")
    if condition:
        break
    condition = True

```