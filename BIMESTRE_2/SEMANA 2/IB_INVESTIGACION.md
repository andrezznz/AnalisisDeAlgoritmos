# 🗓️ Semana 10  
# Algoritmos Voraces – Grafos Dirigidos

## Temas Tratados

- Objetivo  
- Concepto de grafos dirigidos  
- Uso de enfoques voraces  
- Algoritmo de Dijkstra (teoría + pseudocódigo)

---

## 🎯 Objetivo

Profundizar en la aplicación de **algoritmos voraces** sobre **grafos dirigidos**, con especial énfasis en la resolución del **problema de caminos más cortos desde un nodo fuente**. Se busca comprender cómo la dirección de las aristas influye en el proceso de decisión, y por qué algoritmos como **Dijkstra** son herramientas fundamentales en este contexto.

---

## 🔄 Concepto de Grafos Dirigidos

Un **grafo dirigido (digrafo)** está formado por:

- Un conjunto de **vértices** (nodos)
- Un conjunto de **aristas dirigidas** (conexiones con dirección)

Cada arista va desde un nodo origen hacia un nodo destino, es decir, una arista $(A \rightarrow B)$ **no implica** que exista la arista $(B \rightarrow A)$.

### Representación:
- **Lista de adyacencia** con pares ordenados (nodo, peso)
- **Matriz de adyacencia** donde $A[i][j]$ representa el peso desde el nodo $i$ al nodo $j$

Estos grafos se usan en múltiples aplicaciones reales:  
- Redes de carreteras unidireccionales  
- Flujos de datos  
- Modelado de procesos o dependencias

---

## ⚙️ Uso de Enfoques Voraces en Grafos Dirigidos

En grafos dirigidos **con pesos positivos**, los algoritmos voraces son efectivos para determinar rutas eficientes.

### ¿Por qué son adecuados?

- **Selección local óptima**: El algoritmo elige el nodo con menor distancia conocida.
- **Sin retroceso**: No vuelve a evaluar nodos ya procesados.
- **Subestructura óptima**: El camino más corto a un nodo pasa por otros caminos más cortos.
- **Menor complejidad** comparado con métodos exhaustivos o backtracking.

Este tipo de enfoque permite encontrar soluciones **en tiempo polinomial**, siempre que las condiciones del grafo lo permitan (principalmente, ausencia de ciclos negativos).

---

## 🚀 Algoritmo de Dijkstra

Es un algoritmo voraz utilizado para encontrar el **camino más corto desde un nodo fuente** hacia todos los demás nodos en un grafo **dirigido con pesos no negativos**.

### 📌 Requisitos:
- El grafo debe tener **pesos ≥ 0**
- Se necesita una **estructura de prioridad** (como una cola de prioridad o un heap mínimo)

### 🔍 Funcionamiento:

1. Se inicializan las distancias mínimas con infinito (`∞`), excepto la del nodo de inicio que se define como 0.
2. Se utiliza una **cola de prioridad** (por ejemplo, un heap) para explorar los nodos con menor distancia conocida.
3. En cada iteración, se toma el nodo más cercano aún no visitado, y se actualizan las distancias a sus vecinos si se encuentra un camino más corto.
4. El proceso continúa hasta que todos los nodos han sido procesados.

---

## 🧠 Pseudocódigo de Dijkstra

```python
function dijkstra(grafo, nodo_origen):
    Crear distancias_minimas[n] = ∞ para todos los nodos
    distancias_minimas[nodo_origen] = 0
    Crear cola_de_prioridad e insertar (0, nodo_origen)

    Mientras la cola_de_prioridad no esté vacía:
        (dist_actual, nodo_actual) = extraer_nodo_menor_distancia()
        
        Para cada (nodo_vecino, peso) en grafo[nodo_actual]:
            nueva_distancia = dist_actual + peso
            Si nueva_distancia < distancias_minimas[nodo_vecino]:
                distancias_minimas[nodo_vecino] = nueva_distancia
                insertar (nueva_distancia, nodo_vecino) en la cola_de_prioridad

    return distancias_minimas
```
