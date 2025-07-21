# 🗓️ Semana 09  
# Algoritmos Voraces

## Temas Tratados

- Objetivo  
- Características  
- Grafos No Dirigidos  
- Árbol de Expansión Mínima (MST)  
- Algoritmo de Kruskal (teoría + código)

---

## 🎯 Objetivo

Explorar las **características fundamentales** y **principales aplicaciones** de los **algoritmos voraces**, con especial énfasis en su implementación sobre **grafos no dirigidos**. Se busca comprender cuándo este enfoque es apropiado, cómo se compara con otras técnicas (como programación dinámica o backtracking), y de qué manera permite obtener soluciones eficientes, ya sean **óptimas** o **aproximadas**, en problemas complejos.

---

## ⚙️ Características de los Algoritmos Voraces

Los algoritmos voraces construyen soluciones paso a paso, **eligiendo en cada paso la opción que parece más prometedora** (mejor en ese momento), sin reconsiderar decisiones pasadas.

| Característica             | Descripción                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| **Selección local óptima** | En cada paso, se elige la mejor opción posible sin mirar el futuro.         |
| **Sin retroceso**          | Las decisiones no se deshacen, no hay backtracking ni prueba y error.      |
| **Subestructura óptima**   | Los subproblemas forman parte de una solución global óptima.              |
| **Eficiencia computacional** | Suelen tener menor complejidad temporal que otros enfoques más generales.  |
| **Aplicación limitada**    | No todos los problemas se pueden resolver con algoritmos voraces.         |

**Cuándo usar algoritmos voraces:**  
- Cuando el problema cumple con la propiedad de **subestructura óptima** y **greedy choice**.  
- En problemas donde se requiere **velocidad y simplicidad**, y se acepta una solución aproximada si no es óptima.

---

## 🔗 Grafos No Dirigidos

Un grafo no dirigido es una estructura compuesta por vértices conectados por **aristas bidireccionales**. Muchos problemas de optimización sobre grafos pueden beneficiarse del enfoque voraz, como:

- Construcción de Árboles de Expansión Mínima (MST)
- Caminos más cortos desde un nodo fuente (Dijkstra)
- Asignación de recursos (Algoritmo de Huffman)
- Coloración de grafos (versión heurística)

---

## 🌳 Árbol de Expansión Mínima (MST)

Un **árbol de expansión mínima** conecta todos los vértices de un grafo no dirigido, **sin formar ciclos** y con el **menor peso total posible**.

### Algoritmos más conocidos:
- **Kruskal**: selecciona las aristas de menor peso que no formen ciclos.
- **Prim**: construye el árbol añadiendo el nodo más cercano aún no visitado.

---

## 🧮 Algoritmo de Kruskal – Teoría

1. Ordena todas las aristas del grafo según su peso.
2. Inicializa un conjunto disjunto (Union-Find) para gestionar los ciclos.
3. Recorre las aristas ordenadas e incluye la arista si **no forma un ciclo**.
4. Detenerse cuando el MST tenga **n−1 aristas** (donde *n* es el número de nodos).

---

## 💻 Pseudocódigo Optimizado de Kruskal

```java
function kruskal(Grafo G):
    MST = {}  // Árbol de expansión mínima
    crearConjuntosDisjuntos(G.vertices)
    ordenar(G.aristas, porPesoAscendente)

    for (Arista a : G.aristas):
        if (conjuntosDisjuntos(a.origen, a.destino) == false):
            MST.agregar(a)
            unirConjuntos(a.origen, a.destino)

    return MST
```
