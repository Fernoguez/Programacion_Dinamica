# 📈 Conjunto Independiente de Peso Máximo en un grafo de camino simple

Este repositorio implementa la solución al problema del **Conjunto Independiente de Peso Máximo (Maximum Weight Independent Set)** en un **grafo de camino simple**, utilizando **programación dinámica** y una fase de **reconstrucción de la solución**.  
Además, se incluye una **visualización gráfica** de la instancia de entrada y del conjunto óptimo obtenido.

---

##  📌 Descripción del problema

Sea un grafo G = (V, E), donde V = {v1, v2, ..., vn} y cada vértice vi tiene un peso positivo w(vi) > 0. 

Un conjunto independiente es un subconjunto de vértices tal que no existen dos vértices adyacentes dentro del conjunto.

---

### 🎯 Objetivo

El objetivo es encontrar un conjunto independiente S ⊆ V que maximice el peso total.

---

## 🧠 Solución

La solución se divide en dos partes.


### Inciso c) Programación dinámica (Bottom-Up)

Se define un arreglo OPT tal que OPT[i] representa el peso máximo que se puede obtener considerando los vértices {v1, ..., vi}. Las condiciones iniciales son OPT[0] = 0 y OPT[1] = w(v1). La relación de recurrencia utilizada es:

OPT[i] = max( w(vi) + OPT[i-2], OPT[i-1] )

Esta fórmula garantiza que no se seleccionen vértices adyacentes.




### Inciso d) Reconstrucción de la solución

A partir del arreglo OPT, se reconstruye el conjunto independiente óptimo recorriendo los vértices desde n hasta 1. Si w(vi) + OPT[i-2] es mayor que OPT[i-1], entonces el vértice vi se incluye en la solución; en caso contrario, no se selecciona.

---

## 📊 Visualización gráfica

El programa genera una representación gráfica del grafo camino donde los vértices seleccionados se muestran en color verde y los no seleccionados en color gris. Cada vértice muestra su identificador y su peso.


