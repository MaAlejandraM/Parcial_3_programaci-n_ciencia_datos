# Parcial_3_programaci-n_ciencia_datos

# Optimización en Retail Masivo y Monitoreo de Puntos de Venta (ETL & Predictive Modeling)

Este proyecto consiste en el desarrollo de un flujo integral de Ciencia de Datos aplicado al sector de retail masivo y la optimización de cadenas de suministro. El objetivo principal es automatizar la identificación de puntos de venta de alto rendimiento sin depender de revisiones manuales, integrando orquestación de datos y modelos predictivos.

##  Integrantes
* Maria Alejandra Marambio
* Pamela Toro

---

##  Contexto del Negocio
En corporaciones globales, el monitoreo del rendimiento en tiendas es crítico para decisiones estratégicas. Debido al volumen masivo y fragmentado de datos recopilados transaccionalmente y las fluctuaciones macroeconómicas, este sistema implementa procesos **ETL automatizados** y una **API en tiempo real** de conversión monetaria para transformar datos crudos en inteligencia de negocios escalable y libre de errores operativos.

---

##  Tecnologías y Librerías Utilizadas
El proyecto está construido sobre el entorno de Google Colaboratory utilizando las siguientes herramientas core:
* **Pandas & NumPy:** Ingesta, limpieza, manipulación de estructuras tabulares y control de nulos.
* **Requests:** Consumo de APIs REST externas.
* **Matplotlib, Seaborn & Plotly:** Generación de gráficos estadísticos avanzados, visualizaciones dinámicas e interactivas.
* **Scikit-Learn:** (GridSearchCV, Random Forest / Regresión Logística) para entrenamiento, optimización de hiperparámetros y evaluación de modelos predictivos.

---

## Arquitectura del Pipeline ETL

El pipeline centraliza, estandariza y asegura la calidad de las fuentes de información mediante tres etapas principales:

1. **Extracción (Extract):** Ingesta simultánea de dos fuentes independientes: el archivo local `dataset_car_seats.csv` y el tipo de cambio actualizado (USD a CLP) en formato JSON desde **DolarApi**.
2. **Transformación (Transform):** * Aplicación de reglas de negocio y segmentación.
   * **Control de contingencia crítico:** Si la API externa responde con valor cero (0) o falla, el pipeline inyecta automáticamente un valor de contingencia por defecto de `$913.99 CLP`, evitando quiebres en los cálculos financieros del sistema.
   * Creación de la variable objetivo de negocio `HighSales` (Ventas > 8).
3. **Carga (Load):** Generación de un reporte automatizado de consistencia en consola (procesando satisfactoriamente los 400 registros del dataset) y exportación final a un archivo estandarizado llamado `dataset_car.csv`.

---

## Requisitos e Instalación

Para ejecutar este entorno de manera local y reproducible, asegúrate de tener instalado Python 3 y sigue los siguientes pasos:

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/tu-usuario/tu-repositorio.git](https://github.com/tu-usuario/tu-repositorio.git)
   cd tu-repositorio
