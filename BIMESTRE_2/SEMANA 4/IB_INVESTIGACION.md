# 🗓️ Semana 12  
# Algoritmos Divide y Vencerás – Ordenamiento

## Temas Tratados

- Propósito fundamental  
- Definición de "Divide y Vencerás"  
- Algoritmos de Ordenación Principales  
  - Merge Sort  
  - Quick Sort  
- Nociones Clave  
- Beneficios de la Estrategia  
- Fragmento de Código Ilustrativo

---

## 🎯 Propósito Fundamental

Esta unidad busca proporcionar una **comprensión profunda y aplicada** del paradigma **Divide y Vencerás** enfocado en **algoritmos de ordenación**, como **Merge Sort** y **Quick Sort**. Se examinan sus mecanismos, rendimiento, ventajas y escenarios de uso ideal, permitiendo al estudiante dominar herramientas algorítmicas fundamentales para estructuras de datos y algoritmos.

---

## ⚙️ Definición de "Divide y Vencerás"

> Esta es una **estrategia paradigmática** en el diseño de algoritmos, basada en **dividir un problema complejo** en **subproblemas más simples**, resolverlos **recursivamente** y luego **combinar las soluciones parciales** para obtener la solución final del problema original.

### 📌 Etapas Clave:

1. **Dividir:** Fraccionar el problema en subproblemas más pequeños.
2. **Conquistar:** Resolver los subproblemas de manera recursiva.
3. **Combinar:** Integrar las soluciones de los subproblemas para resolver el problema principal.

---

## 🔢 Algoritmos de Ordenación Principales

### 🧩 Merge Sort

> **Merge Sort** (ordenamiento por mezcla) divide repetidamente el arreglo en mitades hasta llegar a subarreglos de un solo elemento. Luego, **fusiona** estas partes de manera ordenada hasta reconstruir el arreglo completo.

#### 🧠 Características:
- Complejidad **O(n log n)** en todos los casos (mejor, promedio y peor).
- Estable (mantiene el orden relativo de elementos iguales).
- Necesita **espacio adicional** para las fusiones.

#### 💻 Ejemplo de implementación en Java:

```java
public class MergeSort {
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int middle = left + (right - left) / 2;
            mergeSort(arr, left, middle);
            mergeSort(arr, middle + 1, right);
            merge(arr, left, middle, right);
        }
    }

    // Combina dos subarreglos ordenados
    static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] izquierda = new int[n1];
        int[] derecha = new int[n2];

        for (int i = 0; i < n1; ++i)
            izquierda[i] = arr[left + i];
        for (int j = 0; j < n2; ++j)
            derecha[j] = arr[mid + 1 + j];

        int i = 0, j = 0, k = left;

        while (i < n1 && j < n2) {
            if (izquierda[i] <= derecha[j]) {
                arr[k] = izquierda[i];
                i++;
            } else {
                arr[k] = derecha[j];
                j++;
            }
            k++;
        }

        while (i < n1) {
            arr[k++] = izquierda[i++];
        }

        while (j < n2) {
            arr[k++] = derecha[j++];
        }
    }
}
```
