#  Semana 05

## 📚 Temas abordados
- Notación Theta (Θ)
- Ejemplos prácticos de Notación Theta
- Notación Asintótica Condicional

---

## 🔁 Notación Theta (Θ)

La notación Θ se emplea para describir un **límite ajustado** del crecimiento de un algoritmo, es decir, establece una **cota inferior y superior simultáneamente**. A diferencia de Big O (que da solo una cota superior) y Big Omega (solo una cota inferior), Theta representa una **descripción exacta** del comportamiento asintótico de un algoritmo.

Cuando decimos que un algoritmo es Θ(f(n)), estamos afirmando que **su tiempo de ejecución crece proporcionalmente a f(n)**, tanto en el mejor como en el peor caso, una medida mucho más precisa de eficiencia.

---

## 🔍 Ejemplos de Notación Theta

- **Θ(1)** – _Tiempo constante_: El algoritmo realiza una operación que no depende del tamaño de la entrada.  
  _Ejemplo: Acceder a un elemento por índice en un arreglo._

- **Θ(n)** – _Tiempo lineal_: El número de operaciones crece proporcionalmente con `n`.  
  _Ejemplo: Recorrer todos los elementos de una lista._

- **Θ(n log n)** – _Tiempo lineal-logarítmico_: Típico en algoritmos de ordenamiento eficientes por comparación.  
  _Ejemplo: Merge Sort, Heap Sort._

- **Θ(n²)** – _Tiempo cuadrático_: El tiempo de ejecución crece con el cuadrado del tamaño de la entrada.  
  _Ejemplo: Bubble Sort en su peor caso._

---

## ⚠️ Notación Asintótica Condicional

Este tipo de análisis considera **condiciones particulares en la entrada** que pueden afectar la complejidad de un algoritmo.

Por ejemplo:
- Un algoritmo con complejidad general **O(n²)** podría comportarse como **O(n)** si la entrada ya está casi ordenada.
- Si ciertos supuestos se cumplen (como la no repetición de elementos), la eficiencia mejora notablemente.

👉 Esta perspectiva es útil para evaluar algoritmos en escenarios reales, donde las entradas no siempre representan el peor caso.

---

## ✅ Conclusión

- **Θ(f(n))** proporciona una medida más precisa del crecimiento real del algoritmo.
- La **notación condicional** permite entender el comportamiento del algoritmo bajo contextos específicos.
- Analizar ambos enfoques mejora la toma de decisiones en diseño y optimización de algoritmos.
