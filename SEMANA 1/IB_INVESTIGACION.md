# Semana 1  
## Algoritmia Elemental – Guía de Estudio

### ¿Qué es un algoritmo?

Un **algoritmo** es un conjunto de pasos definidos y ordenados que permiten resolver un problema o realizar una tarea.  
👉 *Es como una receta para llegar a una solución.*

### Características de un buen algoritmo

- **Entrada:** Recibe datos para trabajar.
- **Salida:** Produce un resultado.
- **Eficiencia:** Usa el menor tiempo y recursos posibles.
- **Adaptabilidad:** Puede ajustarse si cambian las condiciones del problema.

---

### Tipos de algoritmos

- **Algoritmos de búsqueda:**  
  Ej.: Búsqueda lineal, búsqueda binaria.  
  *Sirven para encontrar un valor dentro de un conjunto de datos.*

- **Algoritmos de ordenación:**  
  Ej.: Burbuja (Bubble sort), Quicksort.  
  *Organizan datos en cierto orden (ascendente, descendente, etc.).*

---

### Algoritmos de multiplicación

#### 1. Multiplicación americana

- Multiplicación **de derecha a izquierda**.
- Se hacen productos parciales y se suman al final.

```text
     981
  x 1234
  ------
    3924   ← 981 x 4
   2943    ← 981 x 3 (desplazada 1 lugar)
  1962     ← 981 x 2 (desplazada 2 lugares)
   981     ← 981 x 1 (desplazada 3 lugares)
  ------
1210554
```

#### 2. Multiplicación rusa (o “a la russe”)

- Técnica antigua y creativa.  
- Se usa división entre 2 y multiplicación por 2.  
- Se **suman solo los valores donde el número de la izquierda es impar**.

📋 **Pasos:**

1. Divide el primer número por 2 (sin decimales).
2. Multiplica el segundo número por 2.
3. Tacha las filas donde el número de la izquierda es par.
4. Suma solo los valores de la derecha en filas **impares**.

| Izquierda | Derecha | Sumar |
|-----------|---------|:-----:|
| 981       | 1234    | ✅    |
| 490       | 2468    | ❌    |
| 245       | 4936    | ✅    |
| 122       | 9872    | ❌    |
| 61        | 19744   | ✅    |
| 30        | 39488   | ❌    |
| 15        | 78976   | ✅    |
| 7         | 157952  | ✅    |
| 3         | 315904  | ✅    |
| 1         | 631808  | ✅    |

📌 **Resultado final:**  
`1234 + 4936 + 19744 + 78976 + 157952 + 315904 + 631808 = 1,210,554`

---

### ¿Por qué son importantes los algoritmos?

- Son **la base de cualquier programa o software**.  
- Permiten **resolver problemas de manera clara y eficiente**.  
- Estudiarlos ayuda a **mejorar el pensamiento lógico**.
