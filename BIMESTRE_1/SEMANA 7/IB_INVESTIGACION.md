# Semana 07

## 📚 Temas tratados
- Recurrencias
- Método de Sustitución (Suposiciones Inteligentes)

---

## 🔁 Recurrencias

Una **relación de recurrencia** es una expresión que define una función en términos de sí misma, pero aplicada a **valores más pequeños**. Son fundamentales para describir el tiempo de ejecución de **algoritmos recursivos**, cuya complejidad depende de las llamadas recursivas con tamaños de entrada reducidos.

📌 _Ejemplo clásico_:  
El factorial de `n` puede definirse como:  
`n! = n × (n - 1)!`

Este tipo de ecuaciones permite representar la complejidad de un algoritmo recursivo y, al resolverlas, podemos obtener su comportamiento asintótico en notación O, Θ o Ω.

---

## 🧠 Resolución de Recurrencias

Resolver una recurrencia consiste en encontrar una **forma cerrada** (no recursiva) que describa la función. Existen distintos métodos para lograrlo:

---

## ✅ Método de Sustitución (Suposiciones Inteligentes)

Este método se basa en:

1. **Calcular** los primeros valores de la recurrencia para entradas pequeñas.
2. **Detectar patrones** o regularidades en los resultados.
3. **Proponer una solución tentativa** (forma cerrada) basada en el patrón observado.
4. **Validar la solución** mediante **inducción matemática** u otro método formal.

🔎 Este enfoque permite deducir la forma general de la solución, especialmente cuando los valores muestran regularidad.

---

## ✏️ Otros métodos para resolver recurrencias

### 📐 Ecuación Característica

Aplicable a recurrencias **lineales homogéneas con coeficientes constantes**. Consiste en transformar la recurrencia en una ecuación polinómica, cuyas raíces determinan la estructura de la solución.

---

### 🌳 Método del Árbol de Recursión

Visualiza la recurrencia como un **árbol de llamadas recursivas**, en el que cada nodo representa una subllamada. Se analiza el **costo por nivel** y se suma para obtener el costo total del algoritmo.

---

### 📘 Teorema Maestro

Una herramienta poderosa para resolver recurrencias del tipo:

