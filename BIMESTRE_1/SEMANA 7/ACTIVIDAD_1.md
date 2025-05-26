# 📘 Taller – Resolución de recurrencia

### ✅ Enunciado

Resolver la siguiente recurrencia:

$T(n) = 
\begin{cases}
0 & \text{si } n = 0 \\
2T(n - 1) + 1 & \text{si } n > 0
\end{cases}$

---

## 🔎 Desarrollo paso a paso

Partimos de:

$T(n) = 2T(n - 1) + 1$

Expandimos los primeros términos para encontrar el patrón:

---

$T(n) = 2T(n - 1) + 1$

$= 2[2T(n - 2) + 1] + 1 = 2^2 T(n - 2) + 2 + 1$

$= 2^3 T(n - 3) + 4 + 2 + 1$

$= \dots$

$= 2^k T(n - k) + 2^{k - 1} + 2^{k - 2} + \dots + 2^0$

---

Cuando $k = n$:

$T(n) = 2^n T(0) + \sum_{i = 0}^{n - 1} 2^i$

Dado que $T(0) = 0$, entonces:

$T(n) = \sum_{i = 0}^{n - 1} 2^i$

---

## 📐 Fórmula de suma geométrica

Sabemos que:

$\sum_{i = 0}^{n - 1} 2^i = 2^n - 1$

---

## ✅ Resultado final

$T(n) = 2^n - 1$

---

$\boxed{T(n) = 2^n - 1}$


