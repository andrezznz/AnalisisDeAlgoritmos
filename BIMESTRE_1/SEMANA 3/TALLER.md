> Merge Sort -> CODIGO EN JAVA, con ordenamiento Merge Sort y entrada por consola

```java
import java.util.Scanner;

public class MergeSortHelper {

    // Función de mezcla (merge)
    public static void merge(int[] A, int p, int q, int r) {
        int nL = q - p + 1;
        int nR = r - q;

        int[] L = new int[nL];
        int[] R = new int[nR];

        for (int i = 0; i < nL; i++) {
            L[i] = A[p + i];
        }

        for (int j = 0; j < nR; j++) {
            R[j] = A[q + 1 + j];
        }

        int i = 0, j = 0, k = p;

        while (i < nL && j < nR) {
            if (L[i] <= R[j]) {
                A[k++] = L[i++];
            } else {
                A[k++] = R[j++];
            }
        }

        while (i < nL) {
            A[k++] = L[i++];
        }

        while (j < nR) {
            A[k++] = R[j++];
        }
    }

    // Función recursiva de Merge Sort
    public static void mergeSort(int[] A, int p, int r) {
        if (p < r) {
            int q = (p + r) / 2;
            mergeSort(A, p, q);
            mergeSort(A, q + 1, r);
            merge(A, p, q, r);
        }
    }

    // Programa principal
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingrese la cantidad de elementos: ");
        int n = scanner.nextInt();
        int[] A = new int[n];

        System.out.println("Ingrese los elementos del arreglo:");
        for (int i = 0; i < n; i++) {
            A[i] = scanner.nextInt();
        }

        // Ordenar el arreglo usando Merge Sort
        mergeSort(A, 0, n - 1);

        System.out.println("Arreglo ordenado:");
        for (int i = 0; i < n; i++) {
            System.out.print(A[i] + " ");
        }

        scanner.close();
    }
}
```

# 🧾 Aporte: Implementación de Merge Sort en Java

## 📌 Descripción del desarrollo

Para resolver el problema de ordenar una lista de números ingresada por el usuario, implementé el algoritmo **Merge Sort**, que se basa en la estrategia de **divide y vencerás**. El programa fue estructurado en tres partes principales:

1. **Lectura de datos:**  
   Utilicé la clase `Scanner` para solicitar al usuario el número de elementos y luego los elementos del arreglo.

2. **Ordenamiento con Merge Sort:**  
   Se definió la función recursiva `mergeSort`, que divide el arreglo en subarreglos cada vez más pequeños, hasta llegar a subarreglos de un solo elemento. Luego, con la función `merge`, se combinan las partes ya ordenadas comparando los elementos uno a uno.

3. **Impresión del resultado:**  
   Una vez ordenado, se recorre el arreglo para mostrar los elementos en orden creciente.

---

## ✅ Resultado

El programa solicita los datos al usuario, ordena el arreglo ingresado y muestra la lista ordenada correctamente.

### 💻 Ejemplo de ejecución:

```consola
Ingrese la cantidad de elementos: 5
Ingrese los elementos del arreglo:
4 2 5 1 3

Arreglo ordenado:
1 2 3 4 5
```
