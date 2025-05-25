# Capítulo 1: Preliminares sobre Algoritmos

## 1.1 ¿Qué es un algoritmo?

Un **algoritmo** es una secuencia bien definida de instrucciones que, a partir de una entrada, genera una salida. Está diseñado para resolver problemas específicos de forma lógica y estructurada.

### Ejemplo:

Dada la secuencia de entrada:  
`(0, 20, 90, 10, 3, 2)`  
Un algoritmo que sume todos los elementos devolverá:  
**125**

### Propiedades esenciales de un algoritmo:

- **Entrada:** Datos iniciales que el algoritmo recibe.
- **Salida:** Resultado obtenido tras ejecutar el algoritmo.
- **Precisión:** Cada paso debe estar claramente definido.
- **Finitud:** Debe finalizar tras un número limitado de pasos.
- **Efectividad:** Las operaciones deben ser simples y realizables.

### Notación común en algoritmos:

Se emplea lenguaje matemático, como el álgebra o la teoría de conjuntos.  
Símbolos comunes:

- ℤ → Números enteros  
- ℕ → Números naturales  
- ℝ → Números reales  

---

## 1.2 Algoritmos como tecnología

Los algoritmos son tan fundamentales como el hardware. Su diseño y optimización impactan directamente en el rendimiento de los sistemas, especialmente al procesar grandes volúmenes de datos o ejecutar operaciones matemáticas complejas.

### Diseño de algoritmos

Algunas estrategias comunes:

- **Divide y vencerás:** Divide el problema en subproblemas más pequeños y fáciles de resolver.
- **Algoritmos voraces (Greedy):** Realizan elecciones óptimas en cada paso, con la esperanza de alcanzar la mejor solución global.

---

## Resolución de problemas computacionales

### ¿Qué es un problema computacional?

Un problema computacional está definido por:

- Un conjunto de **entradas válidas**.
- Una **relación** clara entre la entrada y la salida esperada.
- Un **algoritmo** que resuelva correctamente el problema para todas las entradas válidas.

### Ejemplo:

**Problema:** Sumar los primeros `n` números naturales.

- **Algoritmo 1:** Utilizar un bucle que sume del 1 a `n`.
- **Algoritmo 2:** Usar la fórmula directa: `n(n+1)/2`

Ambos algoritmos son correctos, pero el segundo es más eficiente.

---

## Técnicas de abstracción

La **abstracción** permite enfocarse en los aspectos esenciales del problema, ignorando los detalles innecesarios.  

**Ejemplo:**  
Al diseñar un algoritmo de búsqueda, nos enfocamos en la lógica del proceso, no en la representación interna de la memoria.

---
