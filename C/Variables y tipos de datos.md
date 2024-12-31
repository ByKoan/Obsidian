
***Declaración de variables:***

```c
#include <stdio.h>

int main () {
	
	tipo_dato nombre_var = datos;
	return 0;
}
```

***Se pueden declarar varias variables en una misma linea:***

```c
#include <stdio.h>

int main () {

	int x = 5, y = 6, z = 7;
	return 0;
}
```

| TIPO DE DATO       | BITS | OPERADOR           |
| ------------------ | ---- | ------------------ |
| CHAR               | 8    | %c                 |
| Signed Char        | 8    | %c                 |
| Unsigned char      | 8    | %c                 |
| Short              | 16   | %hi o %hd          |
| Short int          | 16   | %hi o %hd          |
| Signed short       | 16   | %hi o %hd          |
| Signed short int   | 16   | %hi o %hd          |
| Unsigned short int | 16   | %hu                |
| Unsigned short int | 16   | %hu                |
| Int                | 16   | %i o %d            |
| Signed int         | 16   | %i o %d            |
| Unsigned int       | 16   | %u                 |
| Long               | 32   | %li o %ld          |
| Signed Long        | 32   | %li o %ld          |
| Unsigned Long      | 32   | %lu                |
| Long long          | 64   | %lli o %lld        |
| Signed Long Long   | 64   | %lli o %lld        |
| Unsigned Long Long | 64   | %llu               |
| Float              |      | %f, %g, %e y %a    |
| Double             |      | %lf, %lg, %le, %la |
| Long double        |      | %lf, %lg, %le, %la |
| Boolean            |      |                    |

***Tenemos también las variables CONSTANTES o variables que no cambian a lo largo del programa:***

```c
#include <stdio,h>

int main () {

	const float pi = 3.14;
	return 0;
}
```