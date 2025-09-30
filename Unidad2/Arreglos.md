Un arreglo es una estructura fundamental que permite almacenar y organizar múltiples datos bajo un mismo nombre, facilitando su acceso y manipulación por medio de índices numéricos. Su uso es imprescindible en programación porque resuelven problemas cotidianos como gestionar listas de compras, calificaciones escolares o los días de la semana.

### ¿Qué son los arreglos?
Un arreglo es una colección ordenada de elementos del mismo tipo, almacenados en memoria de forma contigua, lo que permite acceder fácilmente por posición (índice). Por ejemplo, una lista de temperaturas diarias puede almacenarse en un arreglo de enteros.

### ¿Para qué sirven los arreglos?
Permiten:
- Organizar grandes cantidades de datos relacionados
- Acceder y modificar datos eficientemente usando índices
- Modelar situaciones reales, como horarios de clases o datos sensoriales

### Tipos de arreglos
- Unidimensional: Es como una lista simple, donde cada elemento tiene un índice único.
- Bidimensional: Se asemeja a una tabla, con filas y columnas; útil para representar matrices o tablas de notas.
- Multidimensional: Extiende la idea a más dimensiones, aunque son menos comunes.

| Tipo               | Ejemplo real                        |
|--------------------|-------------------------------------|
| Unidimensional     | Lista de precios de productos|
| Bidimensional      | Tabla de calificaciones     |
| Multidimensional   | Cubo de colores RGB                 |

### ¿Cómo se utilizan?
Debes declarar el arreglo especificando el tipo de datos y el tamaño, luego puedes acceder/modificar los valores usando el índice, comenzando desde 0 en la mayoría de los lenguajes.

***

## Ejemplo práctico en Python
Supongamos que queremos almacenar la cantidad de frutas vendidas durante una semana:

```python
# Arreglo que guarda las ventas de manzanas de cada día
ventas_manzanas = [15, 20, 13, 22, 18, 25, 17]

# Imprimir el total de manzanas vendidas en la semana
total = 0
for venta in ventas_manzanas:    # Recorre cada elemento del arreglo
    total += venta               # Suma cada venta al total
print("Total vendido:", total)   # Muestra el resultado final
```
- `ventas_manzanas = [...]`: Crea un arreglo con las ventas diarias.
- `for venta in ventas_manzanas`: Recorre el arreglo elemento por elemento.
- `total += venta`: Suma cada elemento al acumulado.
- `print(...)`: Muestra el total acumulado.

***

## Ejemplo práctico en C
El mismo ejemplo adaptado a C para sumar ventas de frutas:

```c
#include <stdio.h>
int main() {
    int ventas_manzanas[7] = {15, 20, 13, 22, 18, 25, 17};
    int total = 0, i;
    for (i = 0; i < 7; i++) {             // Recorre cada elemento del arreglo
        total += ventas_manzanas[i];      // Suma cada venta al total
    }
    printf("Total vendido: %d\n", total); // Muestra el resultado final
    return 0;
}
```
- `int ventas_manzanas = {...}`: Declara y define el arreglo de ventas.
- `for (i = 0; i < 7; i++)`: Recorre el arreglo usando índices del 0 al 6.
- `total += ventas_manzanas[i]`: Suma la venta diaria al total.
- `printf(...)`: Imprime el resultado.

***

### ¿En qué casos se utilizan?
- Procesar listas de datos (nombres, notas, productos)
- Modelar secuencias (sensores, eventos diarios)
- Almacenar datos tabulares (calificaciones, imágenes)
- Resolver problemas de lógica y algoritmos (ordenación, búsqueda)

Implementar y comprender arreglos ayuda a adquirir lógica y habilidad para resolver múltiples tipos de problemas en la vida diaria y profesional.
