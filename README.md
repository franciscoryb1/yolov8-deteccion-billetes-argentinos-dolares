# Detección de Billetes Argentinos y Dólares con YOLOv8

## Descripción general
Este proyecto desarrolla un sistema de **detección de objetos** para reconocer billetes de pesos argentinos y dólares estadounidenses en imágenes utilizando **YOLOv8**. La solución se centra en entrenar un modelo ligero (baseline) para identificar denominaciones específicas mediante bounding boxes y etiquetas de clase, con un flujo de trabajo completo que abarca preparación de datos, entrenamiento y validación. El objetivo académico es demostrar la aplicación práctica de visión por computadora en un problema real de clasificación y localización de objetos. El modelo fue entrenado con un conjunto de datos de imágenes etiquetadas y se ejecuta sobre GPU para acelerar el aprendizaje.

## Objetivos del proyecto
- **Detectar billetes de pesos argentinos y dólares estadounidenses** en imágenes con precisión y rapidez.
- **Construir un pipeline reproducible** de entrenamiento y prueba con YOLOv8.
- **Documentar el flujo académico** desde la configuración del dataset hasta la generación de predicciones.

## Alcance funcional
El proyecto abarca:
- **Definición del dataset** mediante un archivo YAML con rutas de entrenamiento/validación y clases.
- **Construcción del dataset** mediante captura y etiquetado manual de imágenes, complementado con técnicas de data augmentation.
- **Entrenamiento del modelo YOLOv8** a partir de un checkpoint preentrenado.
- **Evaluación cualitativa** mediante predicciones sobre imágenes de prueba y guardado de resultados.

## Dataset y clases
El conjunto de datos está compuesto por imágenes de billetes de pesos argentinos y dólares estadounidenses etiquetadas con bounding boxes. Se confeccionó mediante captura y etiquetado manual, y se reforzó con técnicas de **data augmentation** (variaciones de escala, iluminación y rotación) para mejorar la robustez del modelo. El dataset final tiene un tamaño aproximado de **8.000 imágenes**. Las clases contempladas son:
- **$10 pesos**
- **$20 pesos**
- **$50 pesos**
- **$100 pesos**
- **$200 pesos**
- **$500 pesos**
- **$1 USD**
- **$5 USD**
- **$10 USD**
- **$20 USD**
- **$50 USD**
- **$100 USD**

Estas clases se declaran en el archivo de configuración del dataset y son utilizadas directamente por el entrenamiento de YOLOv8.

## Metodología y flujo de trabajo
1. **Montaje del entorno** en Google Colab y validación de GPU para acelerar el entrenamiento.
2. **Construcción del dataset** mediante captura de imágenes, etiquetado manual y data augmentation.
3. **Definición del dataset** mediante un archivo YAML con rutas de entrenamiento y validación.
4. **Entrenamiento supervisado** usando un modelo YOLOv8 preentrenado (por ejemplo, `yolov8n`).
5. **Generación de predicciones** sobre un conjunto de prueba y almacenamiento de imágenes con detecciones y etiquetas de salida.

## Configuración del entrenamiento
El entrenamiento se ejecuta con parámetros académicos estándar para un modelo liviano:
- **Modelo base**: YOLOv8 (variante nano).
- **Épocas**: 50.
- **Tamaño de batch**: 16.
- **Tamaño de imagen**: 640 px.
- **Dispositivo**: GPU (CUDA).

## Tecnologías y herramientas
- **Python** como lenguaje principal.
- **Ultralytics YOLOv8** para entrenamiento e inferencia.
- **PyTorch** como backend de deep learning.
- **Google Colab + Google Drive** para ejecución en la nube y almacenamiento del dataset/resultados.
- **OpenCV / PIL** para manejo básico de imágenes.
- **Notebook Jupyter** para documentación ejecutable del flujo.

## Artefactos generados
- **Modelo entrenado** (`.pt`) almacenado en Google Drive.
- **Imágenes con detecciones** (bounding boxes y etiquetas).
- **Archivos de predicción** en formato de texto con coordenadas y confianza.

## Valor académico
Este trabajo integra conceptos fundamentales de visión por computadora:
- Aprendizaje supervisado con detección de objetos.
- Configuración de datasets en formato YOLO.
- Transfer learning con modelos preentrenados.
- Validación cualitativa de resultados y análisis visual.

## Estado actual
El proyecto cuenta con un flujo completo de entrenamiento y prueba, documentado en un notebook, que permite reproducir el pipeline y analizar los resultados obtenidos en el dataset de billetes.
