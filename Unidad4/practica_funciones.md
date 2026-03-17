# Funciones y manejo de memoria (stack) en C y Python

## Objetivo de la práctica

Comprender, diseñar e implementar **funciones** en programación estructurada,  
analizando su correcta ejecución y **qué ocurre en la memoria (stack)**  
cuando dichas funciones son llamadas. 

Al finalizar la práctica, el alumno será capaz de:

- Diseñar funciones bien definidas y reutilizables.
- Explicar el ciclo de vida de las variables locales.
- Analizar el flujo de ejecución entre funciones.
- Identificar errores comunes relacionados con la stack (pila de ejecución).
- Comparar el manejo de memoria entre **C** y **Python**.

---

## Competencias a desarrollar

- Uso correcto de funciones sin parámetros.
- Uso de funciones con parámetros para operaciones matemáticas simples.
- Implementación de funciones con lógica interna (`if`, `for`).
- Comprensión del flujo del programa mediante funciones que llaman a otras.
- Análisis básico del manejo de memoria (stack y frames de función).
- Pensamiento estructurado y modular. 

---

## Contexto de la actividad

En esta práctica dejarás atrás el código lineal para comenzar a **pensar en términos de funciones**.  
Cada función representa una unidad lógica del programa y, al ejecutarse, ocupa un espacio temporal en la **memoria stack**. 

El énfasis está en que puedas **razonar y explicar**:

- Qué hace cada función.
- Qué datos recibe.
- Qué variables existen en memoria y por cuánto tiempo.
- En qué orden se ejecutan y finalizan las funciones. 

---

## Requerimientos técnicos

- Lenguajes: **C** y **Python**
- Estructura sugerida del proyecto:

```txt
modulo-03/
└── PR-06-funciones-memoria/
    ├── c/
    │   └── main.c
    ├── python/
    │   └── main.py
    └── README.md
```

---

## Uso de IA durante la práctica

La IA puede utilizarse como apoyo para:

- Proponer ejemplos de funciones.
- Revisar claridad del código.
- Sugerir mejoras en nombres y estructura. 

No pegues código generado por IA sin entenderlo. Asegúrate de poder explicar su funcionamiento y el uso de memoria en cada función. 

### Prompt sugerido 1

```txt
Explícame paso a paso qué ocurre en la memoria (stack) cuando esta función
es llamada desde main en C. Usa un lenguaje claro y ejemplos.
```

### Prompt sugerido 2

```txt
Revisa este código en Python y dime si el uso de funciones y parámetros
es correcto desde el punto de vista del flujo y la memoria.
```

El código debe:

- Ejecutarse sin errores.
- Estar comentado.
- Usar nombres claros y descriptivos. 

---

## Práctica 1: Funciones sin parámetros

### Descripción

Funciones que:

- No reciben parámetros.
- No devuelven valores.
- Solo imprimen un mensaje.

### Objetivo conceptual

Entender que:

- Al llamar una función se crea un **frame de función** en la stack.
- Al terminar la función, ese frame se destruye.
- No se intercambia información con el exterior. 

### Ejemplo base en C

```c
#include <stdio.h>

// Función sin parámetros
// Crea un frame en la stack y lo destruye al finalizar
void mostrarMensaje() {
    printf("Hola desde una funcion sin parametros\n");
}

int main() {
    // Se crea el frame de main en la stack
    mostrarMensaje(); // Se crea y destruye el frame de mostrarMensaje
    return 0;
}
```

---

### Ejemplo base en Python

```python
# Función sin parámetros
# No recibe datos ni devuelve valores
def mostrar_mensaje():
    print("Hola desde una funcion sin parametros")

# Llamada a la función
mostrar_mensaje()
```

---

## Práctica 2: Funciones con parámetros (operaciones matemáticas)

### Descripción

Funciones que:

- Reciben parámetros.
- Realizan operaciones matemáticas simples.
- Devuelven un valor.

### Objetivo conceptual

Analizar:

- Cómo los parámetros se copian en el frame de la función (en C).
- Cómo se retorna un valor.
- Por qué las variables locales no existen fuera de la función. 

---

### Ejemplo base en C

```c
#include <stdio.h>

// Función que recibe parámetros y devuelve un valor
int sumar(int a, int b) {
    int resultado = a + b; // Variable local
    return resultado;      // El valor se copia al lugar de llamada
}

int main() {
    int x = 3;
    int y = 5;

    // Se crea el frame de sumar con copias de x e y
    int total = sumar(x, y);

    printf("Resultado: %d\n", total);
    return 0;
}
```

---

### Ejemplo base en Python

```python
def sumar(a, b):
    resultado = a + b
    return resultado

x = 3
y = 5

total = sumar(x, y)
print("Resultado:", total)
```

---

## Práctica 3: Funciones con lógica interna (`if` / `for`)

### Descripción

Funciones que incluyan:

- Condiciones (`if`)
- Repeticiones (`for`)

### Objetivo conceptual

Comprender que:

- El `if` y el `for` no crean nuevos frames de función.
- Las variables del bloque viven dentro del frame de la función.
- La lógica ocurre dentro de una sola llamada. 

---

### Ejemplo con `if` en C

```c
#include <stdio.h>

void esPar(int numero) {
    // numero vive solo dentro del frame de esta función
    if (numero % 2 == 0) {
        printf("El numero es par\n");
    } else {
        printf("El numero es impar\n");
    }
}

int main() {
    esPar(4);
    esPar(7);
    return 0;
}
```

---

### Ejemplo con `for` en Python

```python
def contar(n):
    # i existe solo mientras la función está activa
    for i in range(1, n + 1):
        print(i)

contar(5)
```

---

## Práctica 4: Funciones que llaman a otras funciones

### Descripción

Funciones organizadas jerárquicamente, donde una función coordina a otras.

### Objetivo conceptual

Visualizar:

- Cómo se apilan los frames en la stack.
- El orden de llamadas.
- El orden inverso de retorno. 

---

### Ejemplo base en C

```c
#include <stdio.h>

void preparar() {
    printf("Preparando datos...\n");
}

void procesar() {
    printf("Procesando datos...\n");
}

void mostrar() {
    printf("Mostrando resultados...\n");
}

// Función coordinadora
void ejecutarProceso() {
    preparar();
    procesar();
    mostrar();
}

int main() {
    ejecutarProceso();
    return 0;
}
```

---

### Ejemplo base en Python

```python
def preparar():
    print("Preparando datos...")

def procesar():
    print("Procesando datos...")

def mostrar():
    print("Mostrando resultados...")

def ejecutar_proceso():
    preparar()
    procesar()
    mostrar()

ejecutar_proceso()
```

---

## Actividad de análisis de memoria (obligatoria)

Responder en comentarios o en un archivo `ANALISIS.md`:

1. ¿Qué es un frame de función?
2. ¿Cuándo se crea y cuándo se destruye?
3. ¿Por qué una variable local no puede usarse fuera de su función?
4. ¿Qué diferencia notas entre C y Python al pasar parámetros?
5. ¿Qué ocurre en la stack cuando una función llama a otra? 

---

## Evidencias a entregar

1. `main.c` con todas las prácticas implementadas.
2. `main.py` con las mismas prácticas en Python.
3. Comentarios explicativos en el código.
4. Archivo opcional `ANALISIS.md`. 

---

## Criterios de evaluación (rúbrica resumida)

| Criterio               | Excelente (100%)                         | Aceptable (70%)        | Insuficiente (40% o menos) |
| ---------------------- | ---------------------------------------- | ---------------------- | -------------------------- |
| Uso de funciones       | Funciones claras y bien separadas.       | Funciones funcionales. | Código monolítico.         |
| Parámetros y retorno   | Uso correcto y razonado.                 | Uso básico.            | Uso incorrecto.            |
| Lógica interna         | `if` y `for` bien aplicados.             | Lógica simple.         | Lógica incorrecta.         |
| Flujo entre funciones  | Flujo claro y bien estructurado.         | Flujo comprensible.    | Flujo confuso.             |
| Comprensión de memoria | Explicación clara del stack de ejecución.| Comprensión parcial.   | Sin comprensión.           |

---

Esta práctica busca que el alumno **entienda cómo se ejecuta el programa**,  
no solo que escriba código que “funcione”.

