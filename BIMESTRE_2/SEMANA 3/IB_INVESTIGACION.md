# 🗓️ Semana 11  
# Algoritmos Divide y Vencerás

## Temas Tratados

- Propósito  
- Fundamentos de Divide y Vencerás  
- Mecanismo de la Búsqueda Binaria  
- Implementación en Java

---

## 🎯 Propósito

Asimilar el uso y los beneficios del paradigma algorítmico **Divide y Vencerás**, aplicándolo concretamente en el diseño y comprensión del algoritmo de **búsqueda binaria**. Se busca optimizar el proceso de localización de elementos dentro de **estructuras de datos ordenadas**, mejorando así la eficiencia en tareas frecuentes de búsqueda.

---

## 🧩 Fundamentos de Divide y Vencerás

**Divide y Vencerás (Divide and Conquer)** es una estrategia algorítmica que resuelve problemas complejos dividiéndolos en subproblemas más simples y similares al original. Este enfoque sigue tres pasos clave:

1. **Dividir (Fragmentar):**  
   El problema se separa en uno o más subproblemas más pequeños y manejables.

2. **Conquistar (Resolver):**  
   Se resuelven los subproblemas **recursivamente**. Si los subproblemas son lo suficientemente pequeños, se resuelven directamente.

3. **Combinar (Ensamblar):**  
   Se integran las soluciones parciales para formar una solución completa al problema original.

Este paradigma es muy eficiente y se aplica en algoritmos clásicos como:  
- Búsqueda binaria  
- Merge Sort (ordenamiento por mezcla)  
- Quick Sort (ordenamiento rápido)  
- Exponentiación rápida  
- Algoritmo de Karatsuba para multiplicación de enteros grandes  

---

## 🔍 Mecanismo de la Búsqueda Binaria

La **búsqueda binaria** es un algoritmo altamente eficiente para localizar un valor dentro de un **arreglo ordenado**. Funciona bajo el principio de Divide y Vencerás, ya que en cada paso reduce a la mitad el espacio de búsqueda.

### 📚 Proceso paso a paso:

1. Se calcula el **índice medio** del arreglo o del rango actual.
2. Se compara el valor medio con el **valor buscado**:
   - Si son iguales, se retorna la posición.
   - Si el valor buscado es menor, se repite la búsqueda en la **mitad izquierda**.
   - Si es mayor, se repite en la **mitad derecha**.
3. El proceso se repite hasta que el valor sea encontrado o se agote el rango.

### 📈 Complejidad computacional

- **Mejor caso**: $O(1)$ (el valor está en el medio)
- **Peor y caso promedio**: $O(\log n)$  
Esto se debe a que en cada iteración se reduce el tamaño del problema a la mitad.

### 📌 Condición clave:
El arreglo **debe estar ordenado de forma creciente o decreciente**, según cómo se implemente la lógica.

---

## 💻 Implementación de Ejemplo en Java

```java
public class BusquedaBinaria {
    public static int buscarElemento(int[] arregloOrdenado, int valorBuscado) {
        int limiteInferior = 0;
        int limiteSuperior = arregloOrdenado.length - 1;

        while (limiteInferior <= limiteSuperior) {
            int puntoMedio = limiteInferior + (limiteSuperior - limiteInferior) / 2; // Previene overflow

            if (arregloOrdenado[puntoMedio] == valorBuscado) {
                return puntoMedio; // Elemento encontrado
            } else if (arregloOrdenado[puntoMedio] < valorBuscado) {
                limiteInferior = puntoMedio + 1; // Buscar en la mitad derecha
            } else {
                limiteSuperior = puntoMedio - 1; // Buscar en la mitad izquierda
            }
        }

        return -1; // Elemento no encontrado
    }

    public static void main(String[] args) {
        int[] miArreglo = {2, 4, 6, 8, 10, 12, 14, 16};
        int elementoAEncontrar = 10;
        int resultadoIndice = buscarElemento(miArreglo, elementoAEncontrar);

        if (resultadoIndice != -1) {
            System.out.println("El elemento " + elementoAEncontrar + " fue hallado en el índice: " + resultadoIndice);
        } else {
            System.out.println("El elemento " + elementoAEncontrar + " no está presente en el arreglo.");
        }
    }
}
```
