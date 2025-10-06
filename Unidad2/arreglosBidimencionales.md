Un arreglo bidimensional en ANSI C es una estructura de datos que almacena información en filas y columnas, similar a una matriz matemáticamente. Permite organizar grandes cantidades de datos del mismo tipo, facilitando el acceso y manipulación usando dos índices: uno para la fila y otro para la columna.

Para declarar un arreglo bidimensional, se usa la siguiente sintaxis:
```c
tipo nombre_arreglo[num_filas][num_columnas];
```
Por ejemplo:
```c
int matriz[3][4];
```
Esto crea una tabla de 3 filas por 4 columnas, donde se pueden almacenar 12 datos enteros.

### Inicialización

Un arreglo bidimensional se puede inicializar al momento de declararse:
```c
int matriz[2][3] = {{1, 2, 3}, {4, 5, 6}};
```
El compilador llenará cada elemento de la matriz en el orden de filas y columnas.

### Acceso a los elementos

Para acceder o modificar un elemento, se indica la posición con los dos índices. Por ejemplo, para modificar el elemento de la segunda fila y tercera columna:
```c
matriz[1][2] = 10;
```
Recuerda que los índices inician en cero, así que `matriz[1][2]` corresponde a la fila 2 columna 3.

### Recorrido

Se suelen utilizar bucles `for` anidados para procesar todos los elementos:
```c
for (int i = 0; i < filas; i++) {
    for (int j = 0; j < columnas; j++) {
        printf("%d ", matriz[i][j]);
    }
    printf("\n");
}
```
Esto permite recorrer todas las combinaciones de filas y columnas para leer o modificar datos.

### Ejemplo de uso

Un caso común es registrar varios nombres de hasta 20 caracteres:
```c
char nombres[5][20];
```
Cada fila almacena un nombre diferente, facilitando su manejo y consulta.

En resumen, los arreglos bidimensionales permiten organizar datos complejos en estructuras tabulares dentro de programas en C, facilitando operaciones como procesamiento de matrices, tablas u organización de registros.
```c
#include <stdio.h> // Incluye la biblioteca estándar de entrada/salida para usar printf y scanf

#define NUM_EMPLEADOS 70 // Define una constante para el número de empleados (filas)
#define MAX_NOMBRE 50    // Define una constante para el tamaño máximo de nombre (columnas)

int main() {
    char nombres[NUM_EMPLEADOS][MAX_NOMBRE]; // Declara un arreglo bidimensional para almacenar los nombres de los empleados
    float sueldos[NUM_EMPLEADOS];            // Declara un arreglo para almacenar los sueldos de los empleados
    float suma = 0.0, promedio;              // Inicializa la variable suma y declara promedio
    int i, contador_superior = 0;            // Declara la variable de control 'i' y el contador de sueldos superiores

    // Entrada de datos
    for (i = 0; i < NUM_EMPLEADOS; i++) {    // Ciclo para recorrer cada empleado
        printf("\nEmpleado %d\n", i + 1);   // Muestra el número del empleado (1-indexado)
        printf("Nombre: ");
        scanf(" %[^
]", nombres[i]);        // Lee el nombre (incluye espacios) y lo guarda en la fila correspondiente
        printf("Sueldo: ");
        scanf("%f", &sueldos[i]);           // Lee el sueldo y lo guarda en la posición correspondiente
        suma += sueldos[i];                  // Acumula el sueldo para calcular el total
    }

    // Cálculo del promedio
    promedio = suma / NUM_EMPLEADOS;         // Calcula el promedio dividiendo la suma entre el número de empleados

    // Conteo de sueldos superiores al promedio
    for (i = 0; i < NUM_EMPLEADOS; i++) {    // Recorre todos los sueldos
        if (sueldos[i] > promedio) {         // Si el sueldo es mayor que el promedio
            contador_superior++;             // Incrementa el contador
        }
    }

    // Resultados
    printf("\n===========================================\n");
    printf("Promedio de sueldos: %.2f\n", promedio);                  // Muestra el promedio con dos decimales
    printf("Empleados con sueldo superior al promedio: %d\n", contador_superior); // Muestra el conteo de empleados con sueldo mayor al promedio
    printf("===========================================\n");

    return 0;
}
```
