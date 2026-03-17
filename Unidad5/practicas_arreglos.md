
# Prácticas sobre tipos de arreglos en C y Python

## Objetivo general

Comprender y aplicar el uso de **arreglos** (unidimensionales, bidimensionales, dinámicos) en C y sus equivalentes en Python (listas y listas de listas), analizando su **lógica de programación**, **uso de memoria** y **complejidad algorítmica**. 

Al finalizar, el alumno será capaz de:

- Declarar, inicializar y recorrer arreglos unidimensionales y bidimensionales en C.
- Implementar el equivalente funcional usando listas en Python.
- Utilizar memoria estática y dinámica para arreglos en C.
- Explicar cómo se almacenan estos datos en memoria y cuál es el costo de las operaciones básicas.
- Comparar el comportamiento de arreglos en C con listas en Python. 

---

## Estructura del proyecto

```txt
modulo-03/
└── PR-XX-arreglos/
    ├── c/
    │   └── main.c
    ├── python/
    │   └── main.py
    └── README.md   (este archivo)
```

Trabaja **todo** en `main.c` y `main.py`, separando cada práctica en funciones. 

---

## Reglas generales

- Todo el código debe:
  - Compilar (C) o ejecutarse (Python) sin errores.
  - Estar comentado explicando la lógica, el uso de índices y la memoria.
  - Usar nombres de variables claros y significativos.
- Al final de cada práctica, agrega **un breve comentario** respondiendo preguntas de análisis. 

---

## Práctica 1 – Arreglo unidimensional (vector)

### 1.1 Enunciado

Implementa un programa que:

1. Pida al usuario el tamaño `N` de un arreglo de enteros.
2. Reserve un arreglo de tamaño `N`.
3. Rellene el arreglo con los **múltiplos de un número** dado por el usuario.
4. Muestre todos los elementos del arreglo.
5. Calcule y muestre:
   - La suma de los elementos.
   - El promedio de los elementos. 

### 1.2 Requerimientos en C

- En `main.c`:
  - Implementa una función para:
    - Leer `N` y el número base.
    - Rellenar el arreglo.
    - Imprimirlo.
    - Calcular suma y promedio.
- Usa **arreglo estático** si `N` es pequeño (por ejemplo, máximo 100), o **dinámico** con `malloc` si decides permitir tamaños mayores.
- Asegúrate de recorrer el arreglo con un índice desde `0` hasta `N - 1`. 

**Análisis (comentarios en el código):**

- ¿Cuál es la complejidad de acceso a un elemento por índice?  
- ¿Cuál es la complejidad de recorrer todo el arreglo para sumar sus valores?  
- ¿Dónde se almacena el arreglo (stack o heap) en tu solución? 

### 1.3 Requerimientos en Python

- En `main.py`:
  - Usa una **lista** para almacenar los `N` elementos.
  - Implementa funciones equivalentes:
    - Leer `N` y el número base.
    - Rellenar la lista.
    - Imprimirla.
    - Calcular suma y promedio. 

**Análisis (comentarios en el código):**

- ¿Cómo se comporta el tamaño de la lista (puede crecer/disminuir)?  
- ¿Cuál es la complejidad de acceso a un elemento por índice en la lista?  
- ¿Quién se encarga de liberar la memoria en Python? 

---

## Práctica 2 – Arreglo bidimensional (matriz)

### 2.1 Enunciado

Implementa un programa que trabaje con una **matriz de calificaciones**:

1. Pide al usuario:
   - Número de alumnos `A`.
   - Número de parciales `P`.
2. Crea una matriz de tamaño `A x P`.
3. Lee todas las calificaciones.
4. Calcula:
   - El promedio de cada alumno.
   - El promedio de cada parcial.
5. Muestra la matriz y los promedios calculados.

### 2.2 Requerimientos en C

- En `main.c`:
  - Implementa la matriz como:
    - Matriz estática con un tamaño máximo `MAX_ALUMNOS` y `MAX_PARCIALES`, o
    - Matriz dinámica usando:
      - `int **mat;`
      - Una reserva para las filas y para cada fila sus columnas (o la versión optimizada con un solo bloque de datos). 
  - Implementa funciones para:
    - Leer datos en la matriz.
    - Imprimir la matriz.
    - Calcular y mostrar promedios por alumno y por parcial.

**Análisis (comentarios en el código):**

- ¿Cómo se calcula la dirección de `mat[i][j]` en memoria?  
- ¿Cuál es la complejidad de recorrer toda la matriz?  
- ¿Qué cambia en memoria entre una matriz estática y una dinámica? 
### 2.3 Requerimientos en Python

- En `main.py`:
  - Implementa la matriz como una **lista de listas**, donde cada sublista representa las calificaciones de un alumno. 
  - Define funciones para:
    - Leer los datos.
    - Imprimir la tabla de calificaciones.
    - Calcular promedios por alumno y por parcial.

**Análisis (comentarios en el código):**

- ¿Cómo accedes a un elemento en la fila `i`, columna `j`?  
- ¿Cuál es la complejidad de recorrer toda la estructura para calcular los promedios?  
- ¿Es necesario reservar espacio fijo al inicio como en C? ¿Por qué? 

---

## Práctica 3 – Arreglos dinámicos y redimensionamiento

### 3.1 Enunciado

Simula una **lista de tareas pendientes** que puede crecer y encogerse:

1. Empieza con un arreglo vacío de cadenas (tareas).
2. Permite al usuario:
   - Agregar tareas.
   - Eliminar la última tarea.
   - Mostrar todas las tareas actuales.
3. La interacción se hace mediante un menú sencillo en consola. 

### 3.2 Requerimientos en C

- Representa las tareas como **arreglo dinámico de cadenas**:
  - Usa un arreglo de `char *` (punteros a `char`).
  - Cuando agregues una nueva tarea:
    - Usa `realloc` para aumentar el tamaño del arreglo de punteros.
    - Reserva memoria para copiar la cadena de la tarea. 
  - Cuando elimines la última tarea:
    - Libera la memoria de la cadena.
    - Usa `realloc` para reducir el arreglo de punteros.

**Análisis (comentarios en el código):**

- ¿Cuál es la complejidad de agregar una tarea al final con `realloc`?  
- ¿Qué sucede con la memoria si nunca llamas a `free`?  
- ¿En qué casos `realloc` puede mover todo el arreglo a otra zona de memoria? 

### 3.3 Requerimientos en Python

- Implementa la lista de tareas usando una **lista de Python**:
  - Usa `append()` para agregar.
  - Usa `pop()` para eliminar la última tarea.
  - Muestra la lista con un simple recorrido. 

**Análisis (comentarios en el código):**

- ¿Cuál es la complejidad promedio de `append` y `pop` al final en una lista de Python?  
- ¿Necesitas gestionar manualmente la memoria? ¿Por qué?  
- ¿Qué diferencias observas con la implementación en C? 

---

## Preguntas finales de reflexión (obligatorias)

Responde en comentarios al final de cada archivo o en `ANALISIS.md`:

1. ¿Qué ventajas tienen los arreglos estáticos frente a los dinámicos en C?  
2. ¿En qué casos es imprescindible usar arreglos dinámicos?  
3. ¿Por qué el acceso a un arreglo por índice se considera \(O(1)\)?  
4. ¿Qué diferencias prácticas encontraste entre trabajar con arreglos en C y listas en Python para:
   - Arreglos unidimensionales
   - Arreglos bidimensionales
   - Estructuras dinámicas que crecen y disminuyen?  
5. ¿En qué situaciones reales preferirías usar arreglos frente a listas enlazadas u otras estructuras? 

---

## Criterios de evaluación (resumen)

- Correcta implementación de arreglos unidimensionales y bidimensionales en C.
- Correcta implementación de listas y listas de listas en Python.
- Uso adecuado de memoria estática y dinámica en C (incluyendo `free`).
- Comentarios claros sobre memoria y complejidad de operaciones.
- Código legible, modular y bien organizado en ambos lenguajes.



Les compartó una base para que completen la lógica.

c/main.c
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

/*
 * PR-XX – Tipos de arreglos en C
 * Completa la lógica de cada práctica.
 */

/* ===== Práctica 1: Arreglo unidimensional ===== */

void practica1_arreglo_unidimensional() {
    int N;
    int base;

    printf("=== Practica 1: Arreglo unidimensional ===\n");
    printf("Ingresa el tamaño N del arreglo: ");
    scanf("%d", &N);

    printf("Ingresa el numero base para los multiplos: ");
    scanf("%d", &base);

    // TODO: reservar arreglo (estático con límite o dinámico con malloc)
    // TODO: rellenar con múltiplos de base
    // TODO: mostrar arreglo
    // TODO: calcular suma y promedio

    // TODO: liberar memoria si la reserva fue dinámica
}

/* ===== Práctica 2: Matriz bidimensional ===== */

void practica2_matriz_bidimensional() {
    int A; // alumnos
    int P; // parciales

    printf("=== Practica 2: Matriz bidimensional ===\n");
    printf("Numero de alumnos: ");
    scanf("%d", &A);
    printf("Numero de parciales: ");
    scanf("%d", &P);

    // TODO: declarar matriz estática o dinámica (int **mat)
    // TODO: leer calificaciones
    // TODO: mostrar matriz
    // TODO: calcular promedio por alumno y por parcial

    // TODO: liberar memoria si la matriz fue dinámica
}

/* ===== Práctica 3: Arreglo dinámico de cadenas (tareas) ===== */

void mostrar_menu_tareas() {
    printf("\n=== Menu Tareas ===\n");
    printf("1) Agregar tarea\n");
    printf("2) Eliminar ultima tarea\n");
    printf("3) Mostrar tareas\n");
    printf("0) Salir\n");
    printf("Opcion: ");
}

void practica3_arreglo_dinamico_tareas() {
    char **tareas = NULL;
    int cantidad = 0;
    int opcion;

    printf("=== Practica 3: Arreglo dinamico de tareas ===\n");

    do {
        mostrar_menu_tareas();
        scanf("%d", &opcion);
        getchar(); // limpiar salto de linea

        if (opcion == 1) {
            // TODO: pedir una tarea (cadena)
            // TODO: usar realloc para agrandar el arreglo de punteros
            // TODO: reservar memoria para la nueva cadena y copiarla
        } else if (opcion == 2) {
            // TODO: eliminar ultima tarea (free de la cadena y realloc)
        } else if (opcion == 3) {
            // TODO: mostrar todas las tareas
        }

    } while (opcion != 0);

    // TODO: liberar todas las cadenas y el arreglo de punteros
}

int main() {
    int opcion;

    do {
        printf("\n=== Menu principal arreglos C ===\n");
        printf("1) Practica 1: Arreglo unidimensional\n");
        printf("2) Practica 2: Matriz bidimensional\n");
        printf("3) Practica 3: Arreglo dinamico de tareas\n");
        printf("0) Salir\n");
        printf("Opcion: ");
        scanf("%d", &opcion);

        switch (opcion) {
            case 1:
                practica1_arreglo_unidimensional();
                break;
            case 2:
                practica2_matriz_bidimensional();
                break;
            case 3:
                practica3_arreglo_dinamico_tareas();
                break;
            case 0:
                printf("Saliendo...\n");
                break;
            default:
                printf("Opcion no valida\n");
        }
    } while (opcion != 0);

    return 0;
}
```

# python

python/main.py
PR-XX – Tipos de arreglos en Python
Completa la lógica de cada práctica.
```python 

# ===== Práctica 1: Lista (arreglo unidimensional) =====

def practica1_arreglo_unidimensional():
    print("=== Practica 1: Lista unidimensional ===")
    N = int(input("Ingresa el tamaño N de la lista: "))
    base = int(input("Ingresa el numero base para los multiplos: "))

    # TODO: crear lista
    # TODO: rellenar con múltiplos de base
    # TODO: mostrar lista
    # TODO: calcular suma y promedio


# ===== Práctica 2: Lista de listas (matriz) =====

def practica2_matriz_bidimensional():
    print("=== Practica 2: Matriz (lista de listas) ===")
    A = int(input("Numero de alumnos: "))
    P = int(input("Numero de parciales: "))

    # TODO: crear matriz como lista de listas
    # TODO: leer calificaciones
    # TODO: mostrar matriz
    # TODO: calcular promedio por alumno y por parcial


# ===== Práctica 3: Lista dinámica de tareas =====

def mostrar_menu_tareas():
    print("\n=== Menu Tareas ===")
    print("1) Agregar tarea")
    print("2) Eliminar ultima tarea")
    print("3) Mostrar tareas")
    print("0) Salir")
    return input("Opcion: ")

def practica3_lista_tareas():
    tareas = []

    print("=== Practica 3: Lista dinamica de tareas ===")

    while True:
        opcion = mostrar_menu_tareas()

        if opcion == "1":
            # TODO: pedir una tarea y agregar con append
            ...
        elif opcion == "2":
            # TODO: eliminar ultima tarea con pop (si existe)
            ...
        elif opcion == "3":
            # TODO: mostrar todas las tareas
            ...
        elif opcion == "0":
            print("Saliendo de la gestion de tareas...")
            break
        else:
            print("Opcion no valida")


def main():
    while True:
        print("\n=== Menu principal arreglos Python ===")
        print("1) Practica 1: Lista unidimensional")
        print("2) Practica 2: Matriz (lista de listas)")
        print("3) Practica 3: Lista dinamica de tareas")
        print("0) Salir")
        opcion = input("Opcion: ")

        if opcion == "1":
            practica1_arreglo_unidimensional()
        elif opcion == "2":
            practica2_matriz_bidimensional()
        elif opcion == "3":
            practica3_lista_tareas()
        elif opcion == "0":
            print("Saliendo...")
            break
        else:
            print("Opcion no valida")


if __name__ == "__main__":
    main()

```



