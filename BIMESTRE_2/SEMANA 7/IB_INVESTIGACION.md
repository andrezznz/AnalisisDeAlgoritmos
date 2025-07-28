# TEMA 1: Algoritmos Probabilistas  
**Fuente:** *Brassard & Bratley (2006), Capítulo 10*

## 📌 Introducción

En problemas computacionales complejos o con grandes volúmenes de datos, los algoritmos deterministas pueden resultar poco eficientes. En tales casos, los **algoritmos probabilistas** emergen como una alternativa poderosa al incorporar **aleatoriedad controlada** en su lógica. Aunque no siempre garantizan el mismo resultado, su eficiencia promedio los hace ideales para tareas como verificación, simulación o búsqueda rápida.

Este informe presenta una revisión del enfoque probabilista, sus tipos y aplicaciones, siguiendo a Brassard y Bratley (2006).

---

## 🎯 Objetivos

- Explicar qué son los algoritmos probabilistas y su utilidad.
- Diferenciar entre algoritmos tipo *Monte Carlo* y *Las Vegas*.
- Analizar ejemplos representativos.
- Identificar sus principales ventajas y limitaciones.

---

## ⚙️ Desarrollo

### 🔍 ¿Qué son los algoritmos probabilistas?

Un **algoritmo probabilista** utiliza una fuente de números aleatorios como parte de su lógica, lo cual implica que **una misma entrada puede generar resultados diferentes** en distintas ejecuciones.

🔑 A diferencia de los algoritmos deterministas:
- **No siguen siempre el mismo camino**, pero
- **Están diseñados para controlar la aleatoriedad**, ofreciendo soluciones eficientes en promedio.

---

### 🔁 Tipos de algoritmos probabilistas

#### 1. 🧮 Algoritmos Monte Carlo
- **Tiempo de ejecución fijo o acotado**.
- **No garantizan exactitud**, pero tienen una baja probabilidad de error.
- Útiles cuando se tolera un margen de error a cambio de velocidad.

**Ejemplo:**  
El **algoritmo de Miller–Rabin** verifica si un número es primo. No siempre es correcto, pero repetirlo reduce drásticamente el riesgo de error.

#### 2. 🎲 Algoritmos Las Vegas
- **Siempre entregan un resultado correcto**.
- **Tiempo de ejecución aleatorio**: varía según las decisiones tomadas al azar.
- Preferibles cuando no se puede aceptar una respuesta incorrecta.

**Ejemplo:**  
Quicksort con pivote aleatorio: su rendimiento mejora en promedio, sin comprometer la exactitud.

---

### ✅ ¿Cuándo usar algoritmos probabilistas?

Los algoritmos probabilistas son especialmente útiles cuando:
- No existe un algoritmo determinista eficiente.
- Se busca una solución rápida, aunque aproximada.
- El tamaño del problema impide una solución exacta viable.

**Ámbitos de aplicación destacados:**
- 🔐 Criptografía  
- 🔎 Verificación de resultados  
- 🧪 Simulaciones numéricas  
- 🧬 Inteligencia Artificial y análisis de datos

---

### 📌 Ejemplos destacados

| Algoritmo              | Descripción breve                                                                 |
|------------------------|------------------------------------------------------------------------------------|
| **Freivalds**          | Verifica si A × B = C para matrices, sin multiplicar completamente.               |
| **Hashing aleatorio**  | Distribuye elementos en tablas hash para minimizar colisiones.                   |
| **Métodos Monte Carlo**| Estiman integrales o simulan fenómenos físicos/financieros mediante aleatoriedad.|

---

## ✅ Conclusiones

- Los algoritmos probabilistas son una herramienta poderosa para abordar problemas donde la eficiencia es crítica.
- **Monte Carlo**: más rápidos, pero pueden fallar (con baja probabilidad).
- **Las Vegas**: siempre correctos, pero su duración varía.
- Son comunes en áreas como criptografía, simulaciones, IA y análisis de datos.
- Combinan simplicidad, velocidad promedio y adaptabilidad, lo que los convierte en una opción clave en la computación moderna.
