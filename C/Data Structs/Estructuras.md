En C, una **estructura** (o **``struct``**) es una forma de agrupar diferentes [[Tipos_de_datos|tipos de datos]] bajo un mismo nombre, también se le pueden llamar colecciones de datos. Las estructuras permiten crear datos complejos que tienen diferentes miembros o campos, proporcionando una manera eficiente de manejar conjuntos de datos relacionados.

### Definición de una Estructura
Una estructura se define utilizando la palabra clave ```struct```, seguida de un nombre opcional la estructura, y luego un conjunto de miembros o campos entre llaves `{}`. No puede haber varias estructuras con el mismo nombre, pero si  Cada miembro puede ser de un tipo de datos diferente, como `int`, `float`, `char`, [[Arrays_dinamicos_constantes]], e incluso otras estructuras. Se puede usar el ``keyword`` ``typedef`` como se hace en [[Creacion_de_tipos_de_datos]].

```c
struct  Nombre_estructura {
	tipo_dato miembro1;
	tipo_dato miembro2;
	tipo_dato miembro3;
	...
};
```
Ejemplo de creación de una estructura interna dentro de una estructura:
```c
struct  Nombre_estructura1 {
	tipo_dato miembro1_externo;
	struct  Nombre_estructura_interna {
		tipo_dato miembro1_interno;
		tipo_dato miembro2_interno;
		tipo_dato miembro3_interno;
		...
	};
	tipo_dato miembro2_externo;
	...
};
```
### Ejemplo de una Estructura en C y su inicialización.

En la siguiente estructura agruparemos los datos de: día, mes y año:
```c
typedef struct MyDate { 
	int day; 
	int month; 
	int year; 
} MyDate;
```

Inicializar estructura, manera 1:
```c
MyDate hoy = {20, 10, 2006};
```

Inicializar estructura, manera 2:
```c
MyDate hoy = {
	.day  = 20, 
	.month = 10, 
	.year = 2006
};
```
### Acceder a datos de una Estructura
Para acceder a los datos de una estructura basta con poner el nombre de la estructura el nombre del miembro que queramos acceder. Ej:

```c
MyDate.day = 31;
```
### Acceder a datos de una Estructura con [[Punteros]]

Para acceder a los datos de una estructura basta con poner:
```c
nombre_de_la_estructura->nombre_del_miembro 
```

Ejemplo
```c
MyDate hoy = {
	.day  = 10, 
	.month = 9, 
	.year = 2005
};

MyDate *MyDate_ptr = &hoy; // obtener el puntero de "hoy" y almacenarlo en "MyDate_ptr"
MyDate_ptr -> year = 20;   // En el caso de que la var "MyDate_ptr" fuera un puntero,
						   // acceder al miembro "year"
```

### Pasar estructuras a funciones

Pasar por valor
```c
void PrintDate(MyDate fecha_actual) {
	printf(
		"%d / %d / %d",
		fecha_actual.day,
		fecha_actual.month,
		fecha_actual.year
	);
}
```

Pasar por referencia:
```c
void PrintDate(MyDate *fecha_actual) {
	printf(
		"%d / %d / %d",
		fecha_actual->day,
		fecha_actual->month,
		fecha_actual->year
	);
}
```

Cuando pasamos una estructura por valor, es por que nosotros no modificaremos los campos de la estructura normalmente. Cuando la pasamos por referencia, es por que desearemos modificar sus valores.