# 🧮 Generador Automático de Números Pseudoaleatorios en Java

Este programa en Java genera automáticamente una secuencia de números pseudoaleatorios usando el método **congruencial lineal** (LCG). A diferencia de versiones anteriores, **los parámetros de generación se crean de forma aleatoria**, lo que lo hace completamente automatizado y variable en cada ejecución.

---

## 🧾 Código Fuente

```java
import java.util.Random;

public class GeneradorAutomaticoPseudoaleatorio {

    public static void main(String[] args) {
        Random random = new Random();

        // Parámetros generados aleatoriamente
        long semilla = random.nextInt(100000);            // entre 0 y 99,999
        int cantidad = 10 + random.nextInt(41);           // entre 10 y 50
        int rangoMax = 20 + random.nextInt(81);           // entre 20 y 100

        System.out.println("Parámetros aleatorios generados:");
        System.out.println("Semilla     : " + semilla);
        System.out.println("Cantidad    : " + cantidad);
        System.out.println("Rango Máximo: " + rangoMax);

        int[] numeros = generarPseudoaleatorios(semilla, cantidad, rangoMax);

        System.out.println("\nNúmeros pseudoaleatorios generados:");
        for (int num : numeros) {
            System.out.print(num + " ");
        }

        System.out.println("\n\nEstadísticas:");
        System.out.println("Mínimo: " + calcularMinimo(numeros));
        System.out.println("Máximo: " + calcularMaximo(numeros));
        System.out.printf("Promedio: %.2f\n", calcularPromedio(numeros));
    }

    public static int[] generarPseudoaleatorios(long semilla, int cantidad, int rangoMax) {
        long a = 1664525;
        long c = 1013904223;
        long m = (long) Math.pow(2, 32);

        int[] resultados = new int[cantidad];
        long x = semilla;

        for (int i = 0; i < cantidad; i++) {
            x = (a * x + c) % m;
            resultados[i] = (int) (x % (rangoMax + 1));
        }

        return resultados;
    }

    public static int calcularMinimo(int[] arr) {
        int min = arr[0];
        for (int num : arr) {
            if (num < min) min = num;
        }
        return min;
    }

    public static int calcularMaximo(int[] arr) {
        int max = arr[0];
        for (int num : arr) {
            if (num > max) max = num;
        }
        return max;
    }

    public static double calcularPromedio(int[] arr) {
        int suma = 0;
        for (int num : arr) {
            suma += num;
        }
        return (double) suma / arr.length;
    }
}
```
---
### 🧾 Salida
<img width="1912" height="1027" alt="image" src="https://github.com/user-attachments/assets/ebfcc664-1363-4f91-9950-d9c278d2d07f" />

