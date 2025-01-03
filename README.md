# Proyecto de Sincronización con Semáforos, Barreras y Variables Condicionales

## Descripción del Proyecto
Este proyecto ilustra el uso de diferentes mecanismos de sincronización en **programación concurrente**: **semáforos**, **barreras** y **variables condicionales**. Utiliza la biblioteca `pthread` para la creación y gestión de hilos, así como SDL2 para la visualización de un "circuito" donde carros interactúan de manera sincronizada.

---

## Objetivos del Proyecto

- Demostrar cómo diferentes conceptos de sincronización permiten coordinar tareas concurrentes.
- Simular escenarios donde los hilos deben esperar a otros o coordinarse antes de continuar.
- Proveer una representación visual de la sincronización usando SDL2.

---

## Características Principales

1. **Circuito con Variables Condicionales**:
   - Tres carros (azul, amarillo y rojo) compiten en un circuito.
   - El carro rojo solo avanza cuando los carros azul y amarillo han completado sus trayectorias iniciales.

2. **Circuito con Barreras**:
   - Cinco carros comienzan desde diferentes posiciones y deben detenerse en una "barrera" virtual.
   - Una vez que todos los carros llegan a la barrera, continúan hacia la meta.

3. **Circuito con Semáforos**:
   - Simula el acceso controlado a una sección crítica del circuito.

4. **Gráficos Interactivos con SDL2**:
   - Ventanas interactivas que muestran el movimiento de los carros.
   - Representación visual de las barreras y sincronización entre hilos.

---

## Requisitos del Sistema

1. **Librerías Necesarias**:
   - `pthread` (incluida en POSIX).
   - `SDL2` para la visualización gráfica.
2. **Entorno de Ejecución**:
   - Sistema basado en Linux (probado en WSL).

---

## Compilación y Ejecución

1. **Instalar SDL2**:
   ```bash
   sudo apt-get install libsdl2-dev
   ```

2. **Compilar el proyecto**:
   ```bash
   gcc -o cond_variable pth_cond_variable_circuit.c -lpthread -lSDL2
   gcc -o barrier_circuit pth_barrier_circuit.c -lpthread -lSDL2
   gcc -o semaphore_circuit pth_semaphore_circuit.c -lpthread -lSDL2
   ```

3. **Ejecutar cada circuito**:
   - Circuito con variables condicionales:
     ```bash
     ./cond_variable
     ```
   - Circuito con barreras:
     ```bash
     ./barrier_circuit
     ```
   - Circuito con semáforos:
     ```bash
     ./semaphore_circuit
     ```

---

## Descripción de los Archivos

1. **`pth_cond_variable_circuit.c`**:
   - Implementa un circuito donde el carro rojo avanza solo cuando los carros azul y amarillo terminan su recorrido inicial.

2. **`pth_barrier_circuit.c`**:
   - Simula una barrera sincronizada donde cinco carros deben esperar antes de continuar hacia la meta.

3. **`pth_semaphore_circuit.c`**:
   - Utiliza semáforos para controlar el acceso concurrente a una sección crítica del circuito.

---

## Ejemplo de Sincronización

### Variables Condicionales

- Los carros azul y amarillo avanzan simultáneamente hacia la meta.
- Una vez completado su recorrido, notifican al carro rojo para que continúe.

### Barreras

- Todos los carros comienzan a avanzar hacia una "barrera" virtual.
- Deben esperar hasta que todos los carros lleguen a la barrera antes de continuar.

### Semáforos

- Los carros deben esperar su turno para acceder a una sección crítica compartida del circuito.

---

## Autor
**Jonathan Sampera**



