
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

# Ejercicios
### Arreglos unidimensionales

#### 1. **Optimización de rutas de entrega para una florería**

Una florería recibe diariamente pedidos para entregar en diferentes colonias de la ciudad. Cada pedido tiene una distancia (en km) desde la tienda. El dueño quiere optimizar la ruta diaria para minimizar el tiempo y el gasto de gasolina.

- **Tarea:** Dado un arreglo con las distancias de los pedidos del día, implementa un programa que:
    - Ordene las distancias de menor a mayor (sin usar funciones de librería).
    - Calcule la distancia total recorrida si se visitan en ese orden.
    - Identifique si hay pedidos con la misma distancia y cuántos son.
    - **Reto adicional:** Si el repartidor solo puede hacer 3 entregas por viaje, ¿cuántos viajes necesita y cuál es la distancia total recorrida por todos los viajes?

***

#### 2. **Análisis de gastos personales mensuales**

Una persona lleva un registro diario de sus gastos durante un mes (30 días). Quiere analizar sus hábitos para mejorar su ahorro.

- **Tarea:** Con un arreglo de 30 elementos (gastos diarios), el programa debe:
    - Calcular el gasto total y el promedio diario.
    - Detectar los 3 días con mayor gasto y los 3 con menor gasto.
    - Identificar si hay patrones de gasto (por ejemplo, si los fines de semana gasta más).
    - **Reto adicional:** Simula un "reto de ahorro": si cada día que el gasto es menor al promedio se ahorra la diferencia, ¿cuánto se habría ahorrado al final del mes?

***

#### 3. **Gestión de puntuaciones en un torneo de videojuegos**

En un torneo, cada jugador tiene una puntuación final. El organizador quiere premiar a los mejores y analizar la competencia.

- **Tarea:** Dado un arreglo con las puntuaciones de todos los jugadores:
    - Encuentra la puntuación más alta, la más baja y la mediana.
    - Determina cuántos jugadores están por encima del promedio.
    - Identifica si hay empates en los primeros 3 lugares.
    - **Reto adicional:** Si los premios se reparten solo entre los que superan la mediana, ¿cuántos jugadores recibirán premio?

***

###  Arreglos bidimensionales

#### 4. **Control de inventario en una tienda de abarrotes**

Una tienda lleva un registro semanal de ventas de diferentes productos (filas: productos, columnas: días de la semana). El dueño quiere identificar tendencias y optimizar el inventario.

- **Tarea:** Con una matriz de ventas (por ejemplo, 7 productos x 7 días):
    - Calcula el total vendido por producto y por día.
    - Identifica el producto más vendido de la semana y el día con mayor venta total.
    - Detecta si hay productos que nunca se vendieron en algún día.
    - **Reto adicional:** Si el inventario inicial de cada producto es limitado, simula la actualización diaria del inventario y detecta si algún producto se agota antes de terminar la semana.

***

#### 5. **Planificación de horarios escolares**

Una escuela debe asignar salones a diferentes grupos durante la semana (filas: salones, columnas: horas del día). Cada celda indica si el salón está ocupado (1) o libre (0).

- **Tarea:** Con una matriz de disponibilidad:
    - Identifica los horarios con mayor demanda de salones.
    - Detecta si hay algún salón que nunca se usa o que siempre está ocupado.
    - Permite buscar un bloque de horas consecutivas libres para programar un evento especial.
    - **Reto adicional:** Si se agregan nuevos grupos, simula la reasignación de horarios para minimizar los traslapes y maximizar el uso de los salones.

***

#### 6. **Análisis de patrones de consumo de agua en departamentos**

Un edificio de departamentos registra el consumo diario de agua por departamento (filas: departamentos, columnas: días del mes). El administrador busca detectar fugas y promover el ahorro.

- **Tarea:** Con una matriz de consumos:
    - Calcula el consumo total y promedio por departamento y por día.
    - Identifica departamentos con consumos anómalos (por ejemplo, más del doble del promedio).
    - Detecta si hay días con picos de consumo en todo el edificio.
    - **Reto adicional:** Si se implementa una tarifa escalonada, calcula el pago mensual de cada departamento según su consumo.

***

###  Arreglos multidimensionales

#### 7. **Seguimiento de actividad física en una familia**

Una familia de 4 personas registra los minutos de ejercicio realizados cada día durante 4 semanas (arreglo [persona][semana][día]). Quieren comparar su progreso y motivarse.

- **Tarea:**
    - Calcula el total y promedio semanal de ejercicio por persona.
    - Identifica quién fue más constante (menos variación entre días).
    - Detecta la semana con mayor actividad para toda la familia.
    - **Reto adicional:** Si se propone un reto familiar (meta semanal), determina cuántas veces cada persona y la familia en conjunto lograron la meta.

***

#### 8. **Gestión de reservas en un hotel**

Un hotel tiene 3 pisos, cada uno con 10 habitaciones, y registra la ocupación diaria durante un mes ([piso][habitación][día]). El gerente busca optimizar la ocupación y detectar patrones.

- **Tarea:**
    - Calcula la ocupación promedio por piso, por habitación y por día.
    - Identifica habitaciones que nunca se ocuparon o que siempre estuvieron ocupadas.
    - Detecta los días con ocupación máxima y mínima.
    - **Reto adicional:** Si se quiere equilibrar la ocupación, sugiere una redistribución de reservas para el siguiente mes.

***

#### 9. **Monitoreo de calidad del aire en una ciudad**

Se instalan sensores en 5 zonas de la ciudad, cada uno mide 3 contaminantes diferentes cada hora durante una semana ([zona][contaminante][hora]). El gobierno busca identificar riesgos y tomar decisiones.

- **Tarea:**
    - Calcula el promedio y máximo de cada contaminante por zona y por hora.
    - Identifica las zonas y horas con niveles críticos.
    - Detecta si hay correlación entre contaminantes (por ejemplo, si suben juntos en ciertas horas).
    - **Reto adicional:** Si se activa una alerta cuando dos contaminantes superan cierto umbral al mismo tiempo, cuenta cuántas alertas se habrían generado en la semana.