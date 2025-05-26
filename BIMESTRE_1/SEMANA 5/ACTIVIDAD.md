# Universidad Técnica Particular de Loja

### 📚 Análisis de Algoritmos

**Nombre:** María Paula Guallo Zhapa  
**Fecha:** 10/05/2025  
**Docente:** Ing. Hansel Escudero

---

## ✏️ Actividad

**Dado:**

- $f(n) = n^3 + 9n^2 \log(n)$  
- $g(n) = n^2 \log(n)$

### 📌 Objetivos:

- Comprobar si $f(n) \in o(g(n))$
- Comprobar si $f(n) \in \mathcal{O}(g(n))$
- Demostrar formalmente si existe relación de pertenencia entre $f(n)$ y $\mathcal{O}(g(n))$, y también entre $g(n)$ y $\mathcal{O}(f(n))$, considerando:
  - $f(n) = 2^n$
  - $g(n) = 2^{2n}$

---

## 🔻 Primera Parte

**Dado:**

- $f(n) = n^3 + 9n^2 \log(n)$  
- $g(n) = n^2 \log(n)$

### 🔍 Comprobación: ¿$f(n) \in \mathcal{O}(g(n))$)?  
**No**, veamos por qué:

---

Dadas las funciones:

- $f(n) = n^3 + 9n^2 \log(n)$  
- $g(n) = n^2 \log(n)$

Dividimos ambas funciones:

$f(n) / g(n) = \dfrac{n^3 + 9n^2 \log(n)}{n^2 \log(n)}$

Separando términos:

$f(n) / g(n) = \dfrac{n^3}{n^2 \log(n)} + \dfrac{9n^2 \log(n)}{n^2 \log(n)}$

Simplificando:

$f(n) / g(n) = \dfrac{n}{\log(n)} + 9$

Analizamos el comportamiento asintótico:

$\lim_{n \to \infty} \left( \dfrac{n}{\log(n)} + 9 \right) = \infty$

Entonces:

$\lim_{n \to \infty} \dfrac{f(n)}{g(n)} = \infty$

✅ Por lo tanto, **$f(n) \notin \mathcal{O}(g(n))$**

