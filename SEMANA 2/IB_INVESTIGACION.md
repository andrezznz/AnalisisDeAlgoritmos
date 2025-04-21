# 📘 Demostración por Inducción Matemática

**Objetivo:**  
Demostrar propiedades acerca de corrección y eficiencia de algoritmos (y también fórmulas matemáticas generales).

---

## 🔷 Principio de Inducción Matemática

La inducción matemática es una técnica de demostración usada para probar que una proposición es verdadera para todos los números naturales a partir de un cierto valor.  
Consiste en tres pasos:

1. **Caso base:** Verificar que la fórmula es verdadera para un valor inicial (generalmente \( n = 1 \)).  
2. **Hipótesis de inducción:** Suponer que la fórmula es cierta para \( n = k \).  
3. **Paso inductivo:** Demostrar que, si se cumple para \( n = k \), entonces también se cumple para \( n = k+1 \).

---

## 📘 Ejemplo: Demostrar que

```math
\sum_{i=1}^{n} i = 1 + 2 + 3 + \dots + n = \frac{n(n+1)}{2}
```

---

### ✅ Paso 1: Caso base \( n = 1 \)

Verificamos si se cumple la fórmula cuando \( n = 1 \):

```math
[
sum_{i=1}^{1} i = 1
]

[
frac{1(1+1)}{2} = \frac{2}{2} = 1
]
```

✅ Se cumple el caso base.

---

### ✳️ Paso 2: Hipótesis de Inducción

Suponemos que la fórmula es cierta para un valor \( n = k \), es decir:

```math
[
1 + 2 + 3 + \dots + k = \frac{k(k+1)}{2}
]
```

Esto es nuestra **hipótesis inductiva**.

---

### 🔁 Paso 3: Demostración para \( n = k+1 \)

Queremos probar que:

```math
[
1 + 2 + 3 + \dots + k + (k+1) = \frac{(k+1)(k+2)}{2}
]
```
Usamos la hipótesis de inducción:

```math
[
(1 + 2 + 3 + \dots + k) + (k+1) = \frac{k(k+1)}{2} + (k+1)
]
```

Operamos:

```math
[
frac{k(k+1)}{2} + \frac{2(k+1)}{2} = \frac{k(k+1) + 2(k+1)}{2}
]
```

Factorizamos:

```math
[
frac{(k+1)(k + 2)}{2}
]
```

✅ Esto es exactamente lo que queríamos demostrar.

---

## ✅ Conclusión

Por el principio de inducción matemática, se cumple que:

```math
[
1 + 2 + 3 + \dots + n = \frac{n(n+1)}{2} \quad \text{para todo } n \in \mathbb{N}
]
```

---

> 💡 Puedes aplicar esta técnica para demostrar muchas propiedades relacionadas con sumas, productos, recursiones y algoritmos.

