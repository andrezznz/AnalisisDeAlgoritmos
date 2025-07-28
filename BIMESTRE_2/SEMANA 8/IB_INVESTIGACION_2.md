# 🌳 Aplicación para encontrar el Árbol de Recubrimiento Mínimo (MST) con Kruskal

## 📝 Descripción

Esta aplicación en Java implementa el algoritmo de **Kruskal** para hallar el **Árbol de Recubrimiento Mínimo** (MST) de un **grafo no dirigido y ponderado**. Utiliza el enfoque de **Union-Find (Disjoint Set)** para evitar ciclos, y muestra **paso a paso** cómo se construye el árbol con mensajes de inclusión o descarte de aristas.

Se incluye una prueba de escritorio basada en un grafo con 6 nodos y 9 aristas, mostrando el proceso de selección de aristas y el costo total del MST.

---

## 💻 Código Java Completo

```java
import java.util.*;

public class KruskalApp {

    static class Arista implements Comparable<Arista> {
        int origen, destino, peso;

        Arista(int origen, int destino, int peso) {
            this.origen = origen;
            this.destino = destino;
            this.peso = peso;
        }

        public int compareTo(Arista otra) {
            return this.peso - otra.peso;
        }

        public String toString() {
            return "(" + origen + " - " + destino + ") peso: " + peso;
        }
    }

    static class UnionFind {
        int[] padre;

        UnionFind(int n) {
            padre = new int[n];
            for (int i = 0; i < n; i++) padre[i] = i;
        }

        int encontrar(int u) {
            if (padre[u] != u)
                padre[u] = encontrar(padre[u]); // Path compression
            return padre[u];
        }

        void unir(int u, int v) {
            int raizU = encontrar(u);
            int raizV = encontrar(v);
            if (raizU != raizV)
                padre[raizV] = raizU;
        }
    }

    static List<Arista> kruskal(int n, List<Arista> aristas) {
        List<Arista> resultado = new ArrayList<>();
        Collections.sort(aristas);
        UnionFind uf = new UnionFind(n);

        System.out.println("Ordenando aristas por peso:");
        for (Arista a : aristas) System.out.println(a);

        System.out.println("\nConstruyendo el Árbol de Recubrimiento Mínimo (MST):");
        for (Arista arista : aristas) {
            int raiz1 = uf.encontrar(arista.origen);
            int raiz2 = uf.encontrar(arista.destino);
            if (raiz1 != raiz2) {
                resultado.add(arista);
                uf.unir(raiz1, raiz2);
                System.out.println("✓ Añadida: " + arista);
            } else {
                System.out.println("✗ Descartada (ciclo): " + arista);
            }
        }
        return resultado;
    }

    public static void main(String[] args) {
        int n = 6; // Número de nodos
        List<Arista> aristas = new ArrayList<>();

        // Grafo de prueba
        aristas.add(new Arista(0, 1, 4));
        aristas.add(new Arista(0, 2, 4));
        aristas.add(new Arista(1, 2, 2));
        aristas.add(new Arista(1, 3, 5));
        aristas.add(new Arista(2, 3, 5));
        aristas.add(new Arista(2, 4, 11));
        aristas.add(new Arista(3, 4, 2));
        aristas.add(new Arista(3, 5, 1));
        aristas.add(new Arista(4, 5, 7));

        List<Arista> mst = kruskal(n, aristas);

        System.out.println("\n🔗 Árbol de Recubrimiento Mínimo Final:");
        int total = 0;
        for (Arista a : mst) {
            System.out.println(a);
            total += a.peso;
        }
        System.out.println("Costo total del MST: " + total);
    }
}
```

---

### 💻 Salida
<img width="1917" height="1030" alt="image" src="https://github.com/user-attachments/assets/d9bbc04f-ab6b-4efc-88a2-172e09f77d70" />
