# 🚦 Aplicación para Determinar el Camino Mínimo en un Grafo Dirigido (Algoritmo de Dijkstra)

## 📝 Descripción

Esta aplicación en Java permite calcular el **camino más corto desde un nodo origen a todos los demás** en un grafo dirigido y ponderado, usando el algoritmo de **Dijkstra**. El grafo se representa con una matriz de adyacencia y se muestra la distancia más corta desde el nodo de origen a cada nodo destino.

---

## 💻 Código Java Completo

```java
import java.util.*;

public class DijkstraApp {

    static final int INF = Integer.MAX_VALUE;

    // Algoritmo de Dijkstra
    public static void dijkstra(int[][] grafo, int origen) {
        int n = grafo.length;
        int[] dist = new int[n];          // Distancia mínima desde el origen
        boolean[] visitado = new boolean[n];
        int[] previo = new int[n];        // Para reconstruir el camino

        Arrays.fill(dist, INF);
        Arrays.fill(previo, -1);
        dist[origen] = 0;

        for (int i = 0; i < n - 1; i++) {
            int u = minimoNoVisitado(dist, visitado);
            visitado[u] = true;

            for (int v = 0; v < n; v++) {
                if (!visitado[v] && grafo[u][v] != 0 && dist[u] != INF &&
                    dist[u] + grafo[u][v] < dist[v]) {
                    dist[v] = dist[u] + grafo[u][v];
                    previo[v] = u;
                }
            }
        }

        // Mostrar resultado
        System.out.println("Nodo origen: " + origen);
        for (int i = 0; i < n; i++) {
            System.out.print("Destino " + i + ": distancia mínima = " + dist[i]);
            System.out.print(" | Camino: ");
            imprimirCamino(previo, i);
            System.out.println();
        }
    }

    // Función auxiliar para encontrar el nodo no visitado con menor distancia
    public static int minimoNoVisitado(int[] dist, boolean[] visitado) {
        int min = INF, index = -1;
        for (int i = 0; i < dist.length; i++) {
            if (!visitado[i] && dist[i] < min) {
                min = dist[i];
                index = i;
            }
        }
        return index;
    }

    // Función auxiliar para imprimir el camino desde el origen hasta el nodo destino
    public static void imprimirCamino(int[] previo, int j) {
        if (j == -1) return;
        imprimirCamino(previo, previo[j]);
        System.out.print(j + " ");
    }

    public static void main(String[] args) {
        int[][] grafo = {
            // 0   1   2   3   4
            { 0, 10,  0,  5,  0 }, // 0
            { 0,  0,  1,  2,  0 }, // 1
            { 0,  0,  0,  0,  4 }, // 2
            { 0,  3,  9,  0,  2 }, // 3
            { 7,  0,  6,  0,  0 }  // 4
        };

        dijkstra(grafo, 0);
    }
}
```

---

### 💻 Salida
<img width="1917" height="1026" alt="image" src="https://github.com/user-attachments/assets/50bf44fe-168e-4b6d-8186-6d77ccab6f08" />
