# 📘 Taller 2 — Serie de Fibonacci

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

> Pasos hechos en el cuaderno de Trabajo
![Imagen de WhatsApp 2025-05-29 a las 09 29 49_9ea83aea](https://github.com/user-attachments/assets/f7df9b4f-a15c-4776-9165-646920f8e292)
