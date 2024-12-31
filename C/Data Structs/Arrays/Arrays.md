***Los Arrays o Listas son métodos para guardar múltiples datos/valores en una sola "variable":***

```c
int Numeros[4] = {25, 50, 75, 100};
```

***Se componen de posiciones (En programación siempre empezando desde 0) por lo que para recorrerlas podremos usar un bucle [[Bucles_For|for]]:***

```c
#include <stdio.h>

int main () {

int numeros[4] = {25, 50, 75, 100};

for (int i = 0; i = 4; i++) { // Forma "vaga" ya que habria que sacar la longitud del array
	printf("%d\n", numeros[i]);
}

return 0;
}
```

***Si queremos cambiar el valor de una posición como hemos echo en el bucle for seria de la siguiente manera:***

```c
int numeros[4] = {25, 50, 75, 100};
numeros[0] = 33; // Cambiamos la primera posicion (25) a 33
```

### Obtener longitud del array:

- ***Para obtener la longitud del array C nos proporciona una función `sizeof()`:***

```c
int numeros[4] = {10, 25, 50, 75};
printf("%lu", sizeof(numeros));
```

### Matrices (Arrays multidimensionales):

- Las matrices son varios arrays en uno, como podemos ver en esta foto lo podemos asociar a columnas y filas:
![[Pasted image 20241229141233.png]]

```c
int matriz[2][3] = { {1, 4, 2}, {3, 6, 8} }
```

- ***Para acceder a un elemento de la matriz es muy parecido a un array:***

```c
int matriz[2][3] = { {1, 4, 2}, {3, 6, 8} };

printf("%d", matriz[0][2]);
// Primer corchete indica el array a acceder
// Segundo indica la posicion a acceder
```

### Recorrer una matriz:

```c
int matriz[2][3] = { {1, 4, 2}, {3, 6, 8} };

int i, j;
for (i = 0; i < 2; i++) {
  for (j = 0; j < 3; j++) {
    printf("%d\n", matriz[i][j]);
  }
}
```