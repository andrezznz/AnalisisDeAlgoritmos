# 🗓️ Semana 14  
# Algoritmos Probabilistas

## Temas Tratados

- Propósito de la unidad  
- Definición de Algoritmos Probabilistas  
- Análisis del Tiempo Esperado  
- Ilustración con Búsqueda Aleatoria  
- Exploración de Algoritmos Numéricos  
- El Método de Monte Carlo  
- Otras Técnicas Numéricas  
- Conceptos Fundamentales

---

## 🎯 Propósito de la Unidad

Esta unidad tiene como objetivo **comprender el funcionamiento, análisis y aplicaciones** de los algoritmos que incorporan componentes aleatorios en su ejecución. En particular:

- Analizar su **comportamiento no determinista** y su **tiempo esperado de ejecución**.  
- Estudiar técnicas numéricas como el **método de Monte Carlo**, ampliamente utilizado para **simulaciones, estimaciones estadísticas** y **problemas complejos** donde los métodos deterministas son poco eficientes o impracticables.  
- Introducir la idea de que el azar puede ser una herramienta poderosa y eficiente en el diseño de algoritmos.

---

## 🎲 Definición de Algoritmos Probabilistas

> Son algoritmos que **utilizan aleatoriedad** como parte de su lógica de decisión, lo que significa que, dadas las mismas entradas, pueden producir **resultados diferentes** o tomar **trayectorias distintas** en distintas ejecuciones.

### 📚 Tipos principales:

- **🔹 Algoritmos Las Vegas**  
  - Siempre devuelven una solución **correcta**.
  - El **tiempo de ejecución es variable** debido a su uso de aleatoriedad.
  - Ejemplo: QuickSort aleatorizado.

- **🔸 Algoritmos Monte Carlo**  
  - Suelen ejecutarse en tiempo fijo o acotado.
  - La **respuesta puede ser incorrecta con baja probabilidad**, controlable mediante repeticiones o configuraciones.
  - Ejemplo: Prueba de primalidad probabilista de Miller-Rabin.

---

## ⏱️ Análisis del Tiempo Esperado

> El **tiempo esperado** representa el **promedio ponderado** del tiempo que un algoritmo probabilista requiere para finalizar, tomando en cuenta todas las posibles trayectorias aleatorias que podría seguir.

Este análisis es crucial porque, aunque algunos algoritmos pueden parecer ineficientes en el peor caso, su **desempeño promedio es notablemente superior**.

### 🔍 Fórmula básica:

\[
\mathbb{E}[T] = \sum_{i=1}^{n} P_i \cdot T_i
\]

Donde:  
- \(P_i\) es la probabilidad de que ocurra la trayectoria \(i\)  
- \(T_i\) es el tiempo de ejecución correspondiente a esa trayectoria  

---

## 🔄 Ilustración: Búsqueda Aleatoria

Una forma sencilla de ejemplificar un algoritmo probabilista es a través de una **búsqueda aleatoria**, donde los elementos del arreglo se revisan en posiciones al azar hasta encontrar el valor deseado.

### 💻 Ejemplo en Java:

```java
import java.util.Random;

public class BusquedaAleatoriaEjemplo {
    public int realizarBusquedaAleatoria(int[] arreglo, int valorObjetivo) {
        Random generadorAleatorio = new Random();
        int contadorIntentos = 0;
        boolean[] visitados = new boolean[arreglo.length];

        while (true) {
            int indiceAleatorio = generadorAleatorio.nextInt(arreglo.length);
            contadorIntentos++;

            if (!visitados[indiceAleatorio]) {
                visitados[indiceAleatorio] = true;
                if (arreglo[indiceAleatorio] == valorObjetivo) {
                    return contadorIntentos;
                }
            }

            // Si todos fueron visitados y no se encontró (opcional en versión robusta)
            if (contadorIntentos >= arreglo.length) {
                System.out.println("Todos los elementos han sido inspeccionados.");
                return -1;
            }
        }
    }

    public static void main(String[] args) {
        BusquedaAleatoriaEjemplo buscador = new BusquedaAleatoriaEjemplo();
        int[] datos = {10, 20, 30, 40, 50, 60, 70, 80, 90, 100};
        int objetivo = 50;
        int intentos = buscador.realizarBusquedaAleatoria(datos, objetivo);

        if (intentos != -1) {
            System.out.println("Elemento " + objetivo + " encontrado en " + intentos + " intentos.");
        } else {
            System.out.println("Elemento no encontrado.");
        }
    }
}
```
