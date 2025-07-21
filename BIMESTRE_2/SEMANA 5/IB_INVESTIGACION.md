# 🗓️ Semana 13  
# Algoritmos Divide y Vencerás – Casos Avanzados

## Temas Tratados

- Propósito didáctico  
- Resolución del Problema de la Mediana  
  - Cálculo de la Mediana en Dos Arreglos Ordenados  
- Operaciones con Matrices  
  - Algoritmo de Strassen para Multiplicación  
- Ideas Fundamentales  
- Ilustraciones Prácticas

---

## 🎯 Propósito Didáctico

Este módulo se propone explorar la aplicación del enfoque **Divide y Vencerás** en problemas **computacionalmente más exigentes**, que requieren un nivel superior de eficiencia algorítmica. En particular, se estudian dos casos clave:

- El **cálculo de la mediana** de dos arreglos ordenados.
- La **multiplicación eficiente de matrices** mediante el algoritmo de Strassen.

Ambos problemas sirven como ejemplos poderosos del potencial del enfoque recursivo y estructurado para reducir la complejidad temporal de soluciones tradicionales.

---

## 🔎 Resolución del Problema de la Mediana

### Cálculo de la Mediana en Dos Arreglos Ordenados

> Se desea encontrar la mediana de dos arreglos **ordenados** sin necesidad de fusionarlos completamente. El objetivo es alcanzar una solución con **complejidad O(log(min(n, m)))**, mucho más eficiente que el enfoque ingenuo de O(n + m).

Este algoritmo emplea **búsqueda binaria** sobre el arreglo más corto, dividiendo los arreglos en mitades y garantizando que los elementos a la izquierda del corte sean menores o iguales que los de la derecha.

### 🧠 Supuestos:
- Ambos arreglos están **ordenados en orden ascendente**.
- El tamaño de los arreglos puede ser diferente.
- Se busca la **mediana de la unión hipotética** de ambos arreglos.

### 🧮 Puntos Clave:
- No se combinan los arreglos explícitamente.
- Se realiza una **partición equilibrada** en ambos arreglos.
- El enfoque busca mantener que:
  - `maxIzquierda ≤ minDerecha` en ambas particiones.

### 💻 Ejemplo de implementación en Java (estructura base):

```java
double encontrarMedianaDeArreglosOrdenados(int[] nums1, int[] nums2) {
    if (nums1.length > nums2.length)
        return encontrarMedianaDeArreglosOrdenados(nums2, nums1); // Asegurar que nums1 sea el menor

    int x = nums1.length;
    int y = nums2.length;
    int low = 0, high = x;

    while (low <= high) {
        int partitionX = (low + high) / 2;
        int partitionY = (x + y + 1) / 2 - partitionX;

        int maxLeftX = (partitionX == 0) ? Integer.MIN_VALUE : nums1[partitionX - 1];
        int minRightX = (partitionX == x) ? Integer.MAX_VALUE : nums1[partitionX];

        int maxLeftY = (partitionY == 0) ? Integer.MIN_VALUE : nums2[partitionY - 1];
        int minRightY = (partitionY == y) ? Integer.MAX_VALUE : nums2[partitionY];

        if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
            if ((x + y) % 2 == 0)
                return ((double)Math.max(maxLeftX, maxLeftY) + Math.min(minRightX, minRightY)) / 2;
            else
                return (double)Math.max(maxLeftX, maxLeftY);
        } else if (maxLeftX > minRightY) {
            high = partitionX - 1;
        } else {
            low = partitionX + 1;
        }
    }

    throw new IllegalArgumentException("Input arrays not sorted properly");
}
```
