# Detección de Imágenes Generadas por IA con CNNs (CIFAKE)

Proyecto de **Deep Learning** que entrena una Red Neuronal Convolucional (CNN) para clasificar imágenes como **REALES** o **generadas por IA (FAKE)**, utilizando el dataset [CIFAKE](https://www.kaggle.com/datasets/birdy654/cifake-real-and-ai-generated-synthetic-images). El modelo baseline alcanza una **exactitud del 92.87%** y un **F1-Score macro de 0.93** sobre 20,000 imágenes de prueba.

## 🎥 Video de presentación

> **[▶ Enlace al video de presentación en YouTube](https://www.youtube.com/watch?v=5t-ifwUxIcY)**

## Descripción

El sistema recibe una imagen RGB de 32×32 píxeles y emite una predicción probabilística sobre su naturaleza (REAL o FAKE). La solución cubre el ciclo de vida completo del dato: ingesta, preprocesamiento, entrenamiento y evaluación, organizada en notebooks numerados y autónomos.

- **Dataset:** CIFAKE — 120,000 imágenes balanceadas (50% reales de CIFAR-10, 50% sintéticas de Stable Diffusion v1.4).
- **Arquitectura:** CNN secuencial (Conv2D → MaxPooling → Dropout 0.5 → Dense sigmoide).
- **Frameworks:** TensorFlow / Keras, scikit-learn, kagglehub.

## ▶ Ejecución en Google Colab

Los notebooks están diseñados para ejecutarse en Google Colab **sin errores** y de forma independiente. Para cada notebook:

1. Abre [Google Colab](https://colab.research.google.com/) e importa el notebook (`Archivo → Subir notebook`).
2. Ejecuta las celdas en orden (`Entorno de ejecución → Ejecutar todo`).
3. La descarga del dataset se realiza automáticamente con `kagglehub` dentro del notebook; no es necesario subir archivos manualmente.

> **Orden recomendado:** ejecutar `03` antes que `04` para generar el archivo `modelo_cifake.keras`. Si se ejecuta `04` de forma aislada, este entrena un modelo automáticamente como respaldo.

> **Nota sobre Kaggle:** si `kagglehub` solicita credenciales, sigue las indicaciones en pantalla para autenticarte con tu cuenta de Kaggle.

## 📁 Estructura del proyecto

```
.
├── 01 - exploración de datos.ipynb        # Ingesta, carga y visualización de muestras
├── 02 - preprocesado.ipynb                # Normalización (÷255) y cache/prefetch
├── 03 - arquitectura de linea de base.ipynb  # CNN, entrenamiento (10 épocas) y guardado
├── 04 - evaluacion_y_resultados.ipynb     # Matriz de confusión, reporte y curva ROC
├── INFORME_PROYECTO.PDF                    # Informe final del proyecto
├── ENTREGA1.PDF                            # Documento de la Entrega 1
└── README.md
```

## 📊 Resultados principales

| Métrica | Valor |
|---------|-------|
| Exactitud (Accuracy) | 92.87% |
| F1-Score macro | 0.93 |
| Recall (FAKE) | 0.95 |
| Precision (REAL) | 0.94 |
| Pérdida de validación | 0.2324 |

## Autores

- Camilo Benavides Ramírez
- Brayan Santiago Ramírez Silva
- Mariana Velásquez Velásquez

*Universidad de Antioquia — Facultad de Ingeniería*
