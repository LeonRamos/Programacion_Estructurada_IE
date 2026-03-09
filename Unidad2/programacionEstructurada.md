
---

## 1. El Concepto de Programación Estructurada

La **programación estructurada** es un paradigma basado en la idea de que cualquier programa puede escribirse utilizando solo tres estructuras básicas. Su objetivo es que el código sea claro, fácil de leer y de mantener, evitando el famoso "código espagueti" (saltos desordenados sin lógica aparente).

### Los Tres Pilares

1. **Secuencia:** Las instrucciones se ejecutan una tras otra.
2. **Selección (Estructuras de Control):** El programa decide qué camino tomar según una condición.
3. **Iteración (Bucles):** Se repite un bloque de código mientras se cumpla una condición.

---

## 2. Estructuras de Selección (Condicionales)

Permiten bifurcar el flujo del programa. Es el equivalente lógico a un "Si ocurre esto, haz aquello".

### En C (Tipado estático y sintaxis rígida)

C utiliza llaves `{}` para delimitar bloques y requiere paréntesis en las condiciones.

```c
if (edad >= 18) {
    printf("Eres mayor de edad.\n");
} else {
    printf("Eres menor de edad.\n");
}

```

### En Python (Legibilidad y sangría)

Python elimina las llaves y usa la **indentación** (espacios) para saber qué código pertenece a la condición.

```python
if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")

```

---

## 3. Estructuras de Iteración (Bucles)

Sirven para ejecutar una tarea múltiples veces sin escribir el mismo código una y otra vez.

### El Bucle `While` (Mientras)

Se usa cuando no sabemos exactamente cuántas veces se repetirá el ciclo, solo que depende de una condición.

* **C:** `while (condicion) { ... }`
* **Python:** `while condicion:`

### El Bucle `For` (Para)

* En **C**, el `for` es muy matemático: `for (inicio; condicion; incremento)`.
* En **Python**, el `for` es un **iterador** que recorre elementos de una lista o un rango: `for i in range(5):`.

---

## 4. Diferencias según el Paradigma

Aunque las estructuras de control son las mismas, la forma en que las organizamos cambia drásticamente:

### Programación Secuencial/Estructural

Se enfoca en **procedimientos y funciones**. Los datos y la lógica están separados. Las estructuras de control manipulan variables globales o locales para llegar a un resultado paso a paso.

### Programación Orientada a Objetos (POO)

Aquí, las estructuras de control viven dentro de los **métodos** de un objeto.

* **Dato importante:** En POO, muchas veces usamos polimorfismo para evitar usar demasiados `if/else` complejos, haciendo el código más limpio.

| Característica | Programación Estructurada | Programación Orientada a Objetos |
| --- | --- | --- |
| **Enfoque** | Algoritmos y procesos. | Datos y objetos. |
| **Uso de Estructuras** | Controlan el flujo global del programa. | Controlan el comportamiento de un objeto específico. |
| **Ejemplo** | `calcular_area(radio)` | `circulo.calcular_area()` |

---

## 5. Cuadro Comparativo de Sintaxis

| Estructura | C | Python |
| --- | --- | --- |
| **Bloques** | Definidos por `{ }` | Definidos por indentación `:` |
| **Condicional** | `if (x == 0) { ... }` | `if x == 0:` |
| **Múltiple selección** | `switch (var) { case 1: ... }` | `match var: case 1: ...` (Python 3.10+) |
| **Bucle contado** | `for (int i=0; i<10; i++)` | `for i in range(10):` |

---

> **Nota de reflexión:** Aprender estructuras de control es como aprender las señales de tráfico. No importa si conduces un camión (C) o un deportivo eléctrico (Python), las reglas de cuándo detenerte o girar son universales en la lógica de programación.

