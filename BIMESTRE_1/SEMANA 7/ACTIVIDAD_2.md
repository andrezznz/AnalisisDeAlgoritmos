# 📘 Taller 2 — Serie de Fibonacci

---

## ✅ Enunciado

- Codificar el algoritmo de Fibonacci  
- Identificar las recurrencias  
- Obtener la ecuación general  
- Demostrar

---

## 💻 1. Codificar el algoritmo de Fibonacci (Java)

```java
public class Fibonacci {

    // Función recursiva para calcular Fibonacci
    public static int fibonacci(int n) {
        if (n <= 1)
            return n;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    public static void main(String[] args) {
        int n = 10;
        System.out.println("Serie de Fibonacci:");
        for (int i = 0; i <= n; i++) {
            System.out.print(fibonacci(i) + " ");
        }
    }
}
```

## 🔁 2. Identificar la recurrencia

La secuencia de Fibonacci se define mediante la siguiente relación de recurrencia:

- $F(0) = 0$
- $F(1) = 1$
- $F(n) = F(n - 1) + F(n - 2)$ para $n > 1$

---

## 📐 3. Obtener la ecuación general (Fórmula cerrada)

La **fórmula cerrada** de Fibonacci (conocida como **fórmula de Binet**) es:

$F(n) = \dfrac{1}{\sqrt{5}} \left( \left( \dfrac{1 + \sqrt{5}}{2} \right)^n - \left( \dfrac{1 - \sqrt{5}}{2} \right)^n \right)$

Donde:

- $\phi = \dfrac{1 + \sqrt{5}}{2}$
- $\psi = \dfrac{1 - \sqrt{5}}{2}$

---

## 🧠 4. Demostración por inducción

Queremos demostrar que:

$F(n) = \dfrac{1}{\sqrt{5}}(\phi^n - \psi^n)$

cumple con la definición recursiva de Fibonacci.

---

### 🔹 Paso base:

Para $n = 0$:

$F(0) = \dfrac{1}{\sqrt{5}}(1 - 1) = 0$

Para $n = 1$:

$F(1) = \dfrac{1}{\sqrt{5}}(\phi - \psi) = \dfrac{\sqrt{5}}{\sqrt{5}} = 1$

✅ Se cumple para los casos base.

---

### 🔸 Paso inductivo:

Supongamos que se cumple para $n = k$ y $n = k - 1$:

$F(k) = \dfrac{1}{\sqrt{5}}(\phi^k - \psi^k)$  
$F(k - 1) = \dfrac{1}{\sqrt{5}}(\phi^{k - 1} - \psi^{k - 1})$

Ahora demostramos que también se cumple para $F(k + 1)$:

$F(k + 1) = F(k) + F(k - 1)$

Reemplazamos usando la hipótesis de inducción:

$F(k + 1) = \dfrac{1}{\sqrt{5}}(\phi^k - \psi^k) + \dfrac{1}{\sqrt{5}}(\phi^{k - 1} - \psi^{k - 1})$

Factorizamos:

$F(k + 1) = \dfrac{1}{\sqrt{5}} \left( \phi^k + \phi^{k - 1} - (\psi^k + \psi^{k - 1}) \right)$

Sabemos que $\phi^2 = \phi + 1$ y $\psi^2 = \psi + 1$, entonces:

$\phi^k + \phi^{k - 1} = \phi^{k - 1}(\phi + 1) = \phi^{k + 1}$  
$\psi^k + \psi^{k - 1} = \psi^{k - 1}(\psi + 1) = \psi^{k + 1}$

Entonces:

$F(k + 1) = \dfrac{1}{\sqrt{5}}(\phi^{k + 1} - \psi^{k + 1})$

✅ Por lo tanto, la fórmula se cumple por **inducción matemática**.

