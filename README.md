# Clasificacion-multiclase-de-imagenes-deep-learning

# Tarea 5: Análisis Exploratorio y Preprocesamiento de Imágenes (EDA)

##  Objetivo
Realizar un análisis de datos profundo y preparar un pipeline de preprocesamiento para diferenciar entre dos clases específicas: **Natalie Portman** y **Scarlet Johanson**.

##  Información del Dataset
* **Origen:** [Celebrity Face Image Dataset (Kaggle)](https://www.kaggle.com/datasets/vishesh1412/celebrity-face-image-dataset/data)
* **Clases seleccionadas:**
    1.  Natalie Portman
    2.  Scarlett Johansson

##  Requisitos y Restricciones
* **Librerías Permitidas:** TensorFlow/Keras (o PyTorch), NumPy, Pandas, Matplotlib, Seaborn, OpenCV.
* **Prohibido:** No se ha utilizado `sklearn` en ninguna etapa del procesamiento.

##  Metodología Aplicada

El flujo de trabajo realizado en el notebook adjunto sigue los siguientes pasos:

### 1. Exploración General de Datos
Se realizó una inspección inicial para determinar:
* **Distribución:** Conteo de imágenes por clase para verificar el balance.
* **Formatos:** Validación de extensiones (JPG, PNG, etc.) y resoluciones.
* **Integridad:** Detección de imágenes corruptas, archivos vacíos o ilegibles.
* **Variabilidad:** Observación de condiciones de iluminación, ruido y orientación.

### 2. Análisis Estadístico (Manual)
Sin el uso de librerías de alto nivel para estadística automática, se calculó:
* **Media y Desviación Estándar:** Análisis canal por canal (RGB) útil para la normalización.
* **Rango de Valores:** Verificación de intensidad de píxeles (0-255).
* **Detección de Atípicos:** Identificación de imágenes demasiado oscuras/claras o desenfocadas.

### 3. Limpieza y Control de Calidad
* Eliminación de duplicados.
* Filtrado de archivos corruptos que no pudieron ser decodificados a tensores.
* Corrección de etiquetas si fuera necesario.

### 4. Preprocesamiento
Pipeline de transformación para preparar los datos para una Red Neuronal:
* **Redimensionamiento:** Ajuste de todas las imágenes a un tamaño fijo (ej. `224x224`).
* **Escalado:** Normalización de los valores de píxeles (ej. `Rescaling 1./255`).

### 5. Aumento de Datos (Data Augmentation)
Para evitar el sobreajuste (*overfitting*) y mejorar la capacidad de generalización, se implementaron técnicas como:
* Rotación aleatoria.
* Zoom.
* Volteo horizontal (Horizontal Flip).

##  Resumen de Resultados

> *Nota: Se recomienda ver el notebook para las visualizaciones detalladas.*

* **Total de imágenes originales:** [Inserta cantidad aquí]
* **Total tras limpieza:** [Inserta cantidad aquí]
* **Dimensiones de entrada finales:** [Ej. (224, 224, 3)]
* **Balance de clases:**
    * Natalie Portman: [X] imágenes
    * Scarlet Johanson: [Y] imágenes

##  Instalación y Ejecución

1. Clonar el repositorio.
2. Instalar las dependencias necesarias:
   ```bash
   pip install tensorflow numpy pandas matplotlib seaborn opencv-python
