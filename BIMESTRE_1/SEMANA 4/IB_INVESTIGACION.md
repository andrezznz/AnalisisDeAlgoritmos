# 1. Caracterización del Tiempo de Ejecución y Notación Asintótica

## 1. Introducción

El análisis de algoritmos incluye estudiar su rendimiento en distintos escenarios: mejor caso, peor caso y caso promedio. Para ello, se emplea la **notación asintótica**, que permite describir cómo crece el tiempo de ejecución o el uso de memoria en función del tamaño de la entrada.

Autores como **Cormen et al. (2022)** y **Brassard & Bratley (2006)** ofrecen enfoques complementarios: uno más práctico y otro más formal.

---

## 2. Tema: _Characterizing Running Times_ (Cormen et al., 2022)

### Objetivo
Describir matemáticamente cómo se comporta un algoritmo a medida que aumenta el tamaño de la entrada.

### Puntos clave

#### a) Tiempo de ejecución según el tamaño de entrada
El rendimiento depende del tamaño de la entrada `n`. Se analiza en función de operaciones elementales (no del tiempo real).

#### b) Tipos de análisis
- **Peor caso (Worst-case)**: Tiempo máximo para entradas de tamaño `n`.
- **Caso promedio (Average-case)**: Tiempo esperado considerando todas las entradas posibles.
- **Mejor caso (Best-case)**: Tiempo mínimo (poco útil en la práctica).

#### c) Ejemplo: Búsqueda lineal
Para un arreglo de `n` elementos:
- **Peor caso**: `T(n) = n` (el elemento está al final).
- **Mejor caso**: `T(n) = 1` (el elemento está al principio).
- **Promedio**: `T(n) = n / 2`.

#### d) Funciones de crecimiento
Se utilizan funciones como:
- `n` (lineal)
- `n²` (cuadrática)
- `log n` (logarítmica)
- `n log n` (quasilineal)
- `2ⁿ`, `n!` (exponencial y factorial)

Estas ayudan a clasificar algoritmos por eficiencia.

---

## 3. Comparación: Cormen vs Brassard & Bratley

| **Aspecto**              | **Cormen et al. (2022)**                          | **Brassard & Bratley (2006)**              |
|--------------------------|---------------------------------------------------|---------------------------------------------|
| **Enfoque**              | Práctico, orientado a implementación              | Teórico, enfocado en rigor matemático       |
| **Casos de análisis**    | Mejor, peor y promedio                            | Principalmente comportamiento asintótico    |
| **Notación asintótica**  | Introducción informal y aplicada                  | Definiciones formales y matemáticas         |
| **Ejemplos tratados**    | Búsqueda lineal, funciones comunes de crecimiento | Órdenes de complejidad y comparación formal |
| **Aplicación**           | Diseño y evaluación de algoritmos                 | Fundamentos para la comparación rigurosa    |

---

## 4. Conclusión

El estudio de la eficiencia algorítmica requiere tanto:
- La **visión práctica** de Cormen, útil para diseñar e implementar algoritmos eficientes.
- Como la **formalización matemática** de Brassard & Bratley, esencial para comparar rigurosamente complejidades.
