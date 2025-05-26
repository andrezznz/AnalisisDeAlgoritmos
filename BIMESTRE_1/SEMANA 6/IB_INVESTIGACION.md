# Semana 06

## 📚 Temas tratados
- Notación Theta (Θ)
- Ejemplos de Notación Theta
- Notación Asintótica Condicional
- Análisis de estructuras de control
- Secuencias

---

## 🔁 Notación Theta (Θ)

La notación Θ (Theta) describe un **límite ajustado** para el crecimiento del tiempo de ejecución o uso de recursos de un algoritmo. A diferencia de Big O (cota superior) y Omega (cota inferior), Theta representa **ambas simultáneamente**, lo que permite definir el crecimiento **exacto** del algoritmo.

Esta notación es la más precisa para expresar eficiencia asintótica, ya que describe el comportamiento del algoritmo en el **mejor y peor caso con la misma función**.

---

## 🔍 Ejemplos de Notación Theta

- **Θ(1)** – _Tiempo constante_: El tiempo de ejecución no depende del tamaño de entrada.  
  _Ejemplo: Acceder a un elemento por índice en un arreglo._

- **Θ(n)** – _Tiempo lineal_: El tiempo crece proporcionalmente con el tamaño `n` de la entrada.  
  _Ejemplo: Recorrer una lista completa._

- **Θ(n log n)** – _Tiempo lineal-logarítmico_: Común en algoritmos de ordenamiento eficientes.  
  _Ejemplo: Merge Sort, Heap Sort._

- **Θ(n²)** – _Tiempo cuadrático_: El crecimiento es proporcional al cuadrado del tamaño de entrada.  
  _Ejemplo: Bubble Sort en su peor caso._

---

## ⚠️ Notación Asintótica Condicional

Este análisis considera **casos específicos de entrada** que pueden afectar la complejidad de un algoritmo. A diferencia de la notación tradicional, que analiza el comportamiento general, la versión condicional se adapta a escenarios particulares.

📌 _Ejemplo:_  
Un algoritmo que generalmente es **O(n²)** puede comportarse como **O(n)** si la entrada está casi ordenada o si ciertos valores no se repiten.

🔎 Este enfoque es muy útil en situaciones reales donde las entradas no siguen el patrón del peor caso.

---

## 🧩 Análisis de las Estructuras de Control

El análisis algorítmico se realiza **evaluando el tiempo de ejecución de instrucciones individuales**, combinándolas según la estructura del programa. Las estructuras simples, como secuencias, son directas de analizar. Sin embargo, los bucles y condiciones requieren más atención.

---

## 🔗 Secuencias

Cuando las instrucciones se ejecutan en orden, el tiempo total es la **suma de los tiempos individuales**.

**Fórmula:**  
Si una instrucción toma `T₁` y otra `T₂`, el total será:  
`T_total = T₁ + T₂`

---

## 🔁 Bucles 'Para' (For)

El tiempo de un bucle `para` depende de:

- Número de iteraciones.
- Tiempo de ejecución por iteración.

**Ejemplo:**
```pseudo
para i ← 1 hasta m hacer
    p(i)
```
