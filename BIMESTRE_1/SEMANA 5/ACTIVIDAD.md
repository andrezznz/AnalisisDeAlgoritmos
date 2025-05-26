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

### 🔍 Análisis adicional

Cuando $n \to \infty$, entonces $\dfrac{n}{\log(n)} \to \infty$, por lo tanto:

$\dfrac{f(n)}{g(n)} \to \infty \Rightarrow f(n) \notin \mathcal{O}(g(n))$

---

Esto implica que **$f(n) \notin \mathcal{O}(g(n))$**

---

### 📌 Comprobar si $f(n) \in \mathcal{O}(n^2)$

Calculamos:

$\dfrac{f(n)}{n^2} = \dfrac{n^3}{n^2} + \dfrac{9n^2 \log(n)}{n^2} = n + 9\log(n) \to \infty$

Esto implica que **$f(n) \notin \mathcal{O}(n^2)$**

---

## ✨ Segunda Parte

**Dado:**

- $f(n) = 2^n$
- $g(n) = 2^{2n} = (2^n)^2$

---

### 🔹 Comprobar si $f(n) \in \mathcal{O}(g(n))$

$\dfrac{f(n)}{g(n)} = \dfrac{2^n}{2^{2n}} = \dfrac{1}{2^n} \Rightarrow \lim_{n \to \infty} \dfrac{f(n)}{g(n)} = 0$

✅ Esto implica que **$f(n) \in \mathcal{O}(g(n))$**, porque el cociente tiende a cero.

---

### 🔸 Comprobar si $g(n) \in \mathcal{O}(f(n))$

$\dfrac{g(n)}{f(n)} = \dfrac{2^{2n}}{2^n} = 2^n \to \infty \Rightarrow g(n) \notin \mathcal{O}(f(n))$

---

🔶 Esto implica que **$g(n) \notin \mathcal{O}(f(n))$**, no se comprueba ya que el cociente crece sin límite.

---

