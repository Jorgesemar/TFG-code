# Analisis de posiciones de lucha y detección de los luchadores mediante inteligencia artificial
## Descripción

Versión 2.

**Modelos utilizados:**

Clasificador:  resNet_18

Esqueletos:  HRNet 50

Analisis de secuencia:  LSTM


**Descripción de versión**
Segundo acercamiento al proyecto, aumentando la cantidad de datos y aplicando nuevos filtros para mejorar la estimación de poses.

**Preprocesamiento** 
- El dataset se aumenta la cantidad de datos hasta 76343 (Todo el dataset con los dos peleadores presentes)
- se redimensionan las imagenes.
- se reduce el numero de anotaciones coincidiendo con el numero de imagenes
- se eliminan aquellas imagenes en las que solo aparezcan uno de los dos peleadores.
- Se normalizan las coordenadas de las poses
- Se cambia el color de las imagenes a blanco y negro
- Se aplica el filtro sobel para aumentar el contraste

## Estructura
### Analisis.ipynb:

Analisis de las etiquetas e imagenes ya preprocesadas, inclutendo:

- Analisis de puntos clave de las poses y la distribucion de las confianzas de los mismos. 

- Matriz de transiciones entre posiciones

- Grafico de duración promedio de cada posición
### Generador de video.ipybn:

Pruebas de visualizacion cargando los modelos entrenados. Visualización de los esqueletos, las clases y las predicciones de secuencia "en tiempo real"
### AnalisisSecuencial.ipybn:

Funciones necesarias para el entrenamiento de un modelo LSTM para la predicción de las secuencias de una posición a otra
### Clasificador.ipybn:

Funciones necesarias para el entrenamiento de un modelo resNet 18 para la clasificación de imagenes en base a sus etiquetas. 
### Pose.ipybn

Funciones necesarias para el entrenamiento de un modelo HRNet para prediccion los puntos claves de las poses junto con preprocesamiento adicional. 
### Preprocesamiento.ipybn

Funciones necesarias para el preprocesamiento de las imagenes y etiquetas.
