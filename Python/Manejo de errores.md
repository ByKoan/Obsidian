***En Python al igual que en Java tenemos las palabras claves Try pero no ternemos el Catch si no que tenemos "Except" + el tipo de error que queremos capturar. Un ejemplo:***

```python
while True:
    try: # tratar de hacer algo
        # bloque de codigo a tratar de ejecutar
        print("hOLA")
    except KeyboardInterrupt:
        # que hacer si ocurre un error de tipo KeyboardInterrupt
        print("adios")
        break # finalizar el bucle while infinito
```

***Una vez visto como funciona tenemos los siguientes códigos de error que son los mas comunes:***

```python
"""
        KeyboardInterrupt -> se metio un ctrl +c en tiempo de ejecucion
        TypeError -> error de tipos
        IndentationError -> por meter espacios o tabs de mas
        SyntaxError -> error de sintaxis
        NameError -> cuando el nombre de una var o func no exite o fue mal escrito
    """
```
