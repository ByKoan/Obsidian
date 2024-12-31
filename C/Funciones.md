***Bloques de códigos que realizan una tarea especifica. Se definen y luego se pueden invocar o llamar desde otras partes del programa. Las funciones permiten organizar el código, reutilizarlo y hacer que sea mas modular y fácil de leer***

### Tipos de funciones:
- ***Funciones con valor de retorno:***

```c
int sumar(int a, int b) {
    return a + b;
}
```

- ***Funciones sin valor de retorno (`void`):

```c
void imprimir_saludo() {
    printf("Hola, Mundo!\n");
}
```

### Componentes de la funciones:

- Tipo de retorno
- Nombre de la función
- Parámetros (Argumentos)
- Cuerpo de la función (Código)

### Funciones recursivas:
- ***Aquella que se llama a si misma. Útil para problemas que pueden dividirse en subproblemas similares:***

```c
int factorial(int n) {
    if (n == 0) return 1;  // Caso base
    else return n * factorial(n - 1);  // Llamada recursiva
}
```
