# Implementación del Algoritmo Backpropagation desde Cero

Este repositorio contiene una implementación del algoritmo de **retropropagación (backpropagation)** en Python, desarrollada como componente práctico para un reporte de investigación de la materia de Álgebra Lineal.

El objetivo de este proyecto es demostrar el funcionamiento del algoritmo paso a paso, desde sus fundamentos matemáticos hasta una implementación funcional capaz de resolver problemas no lineales como el XOR.

##  Contexto Académico

Este código fue desarrollado como material complementario para el reporte de investigación "Algoritmo Backpropagation".

- **Institución:** Facultad de Ingeniería - Universidad Nacional de Asunción (FIUNA)
- **Autor:** Juan Miguel Martínez Muñoz

##  Características

El script principal (`backprop_visual.py`) incluye:
* Una clase `NeuralNetwork` construida desde cero utilizando solo **NumPy**.
* Implementación completa del ciclo de aprendizaje:
    1.  **Propagación hacia Adelante** (Feed-forward).
    2.  **Cálculo del Error**.
    3.  **Retropropagación del Error** (Backward Propagation).
    4.  **Actualización de Pesos y Sesgos**.
* Entrenamiento y prueba de la red con el problema clásico **XOR**.
* Una **comparación directa** con la implementación del `MLPClassifier` de la librería Scikit-learn.
* **Visualización de resultados** mediante `matplotlib` para una mejor comprensión del proceso.

##  Requisitos

Para ejecutar este proyecto, necesitas tener instalado Python 3 y las siguientes librerías:

* NumPy
* Scikit-learn
* Matplotlib

Puedes instalarlas fácilmente usando pip:
```sh
pip install numpy scikit-learn matplotlib
```

##  Cómo Ejecutar

1.  Clona este repositorio en tu máquina local.
2.  Navega hasta el directorio del proyecto en tu terminal.
3.  Ejecuta el script de Python:
    ```sh
    python tu_nombre_de_archivo.py
    ```
4.  El script imprimirá el progreso del entrenamiento y los resultados en la consola. Además, guardará dos gráficos en el directorio: `error_history.png` y `decision_boundary.png`.

##  Resultados Esperados

Al ejecutar el script, se mostrará la siguiente salida en la consola, seguida de la generación de dos gráficos.

#### Salida de la Consola
```
Entrenando la red neuronal implementada desde cero...
Época 0, Error: 0.3563
...
Época 9000, Error: 0.0040
Entrenamiento finalizado.

--- RESULTADOS ---
Predicciones del modelo propio (entradas XOR):
Entrada: [0 0], Predicción: 0.0607 -> 0.0
Entrada: [0 1], Predicción: 0.9454 -> 1.0
Entrada: [1 0], Predicción: 0.9463 -> 1.0
Entrada: [1 1], Predicción: 0.0569 -> 0.0

==================================================

Entrenando la red neuronal de Scikit-learn...
Entrenamiento finalizado.

Predicciones del modelo de Scikit-learn (entradas XOR):
Entrada: [0 0], Predicción: 0
Entrada: [0 1], Predicción: 0
Entrada: [1 0], Predicción: 0
Entrada: [1 1], Predicción: 0
```

#### Gráficos Generados

1.  **Evolución del Error:** Muestra cómo el error de la red disminuye a medida que avanzan las épocas de entrenamiento.
    ![Gráfico de Error vs. Épocas](error_history.png)

2.  **Frontera de Decisión:** Visualiza cómo la red ha aprendido a clasificar el espacio de entrada para resolver el problema XOR.
    ![Frontera de Decisión XOR](decision_boundary.png)

### Análisis de Resultados

Se observa una diferencia clave en los resultados:

* La implementación del algoritmo 1  **logró aprender** la función XOR, validando el algoritmo descrito en el reporte.
* El modelo de Scikit-learn, con su inicialización aleatoria específica (`random_state=42`), **no convergió** a la solución correcta. En su lugar, quedó atrapado en un **mínimo local**, aprendiendo una solución subóptima.

Este resultado no indica un error, sino que es una demostración práctica de un desafío fundamental del descenso de gradiente: su alta sensibilidad al punto de partida aleatorio de los pesos.
