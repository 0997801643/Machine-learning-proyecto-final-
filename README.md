# Detección de ataques IoT con Machine Learning — CICIoT2023

Proyecto de Machine Learning: clasificación de tráfico de red IoT en 8 clases (Benign, DDoS, DoS, Mirai, Recon, Spoofing, BruteForce, Web-based) usando el dataset **CICIoT2023**, y comparación estadística entre **Random Forest** y **Regresión Logística**.

**Autor:** Carlos Mateo Velastegui

## Contenido del notebook

1. Introducción
2. EDA (Exploratory Data Analysis)
3. Feature Selection tipo filter (`SelectKBest`)
4. Pipelines de scikit-learn (imputación → escalado → selección → modelo)
5. Optimización de hiperparámetros con *repeated stratified k-fold CV*, curvas de validación y de aprendizaje
6. Comparación estadística de 2 técnicas (Wilcoxon y t-test pareado corregido)
7. Visualización con t-SNE
8. Conclusiones y referencias (IEEE)

## Estructura

```
├── notebooks/
│   └── Mateo_Velastegui_Proyecto_ML_CICIoT2023-FINAL.ipynb
├── data/
│   └── CICIoT2023_muestra_2500_por_clase.csv   # muestra (máx. 2,500 registros por clase)
├── requirements.txt
└── README.md
```

## Dataset

CICIoT2023 — Canadian Institute for Cybersecurity: https://www.unb.ca/cic/datasets/iotdataset-2023.html
(también en Kaggle: `himadri07/ciciot2023`).

El dataset completo (~2.3 GB) no se incluye por su tamaño. En `data/` está la muestra usada en el proyecto.

## Cómo ejecutar

1. Abrir `notebooks/Mateo_Velastegui_Proyecto_ML_CICIoT2023-FINAL.ipynb` en Google Colab.
2. En la celda de configuración elegir la fuente de datos:
   - `DATA_SOURCE = "drive"` para leer train/validation/test desde Google Drive (ajustar `DRIVE_DIR`),
   - `DATA_SOURCE = "muestra"` y subir `data/CICIoT2023_muestra_2500_por_clase.csv` a Colab, o
   - `DATA_SOURCE = "kaggle"` para descargar el dataset completo con `kagglehub`.

   Fuera de Colab, el modo `"drive"` usa automáticamente la muestra local.
3. *Entorno de ejecución → Ejecutar todo*.

## Referencia del dataset

E. C. P. Neto, S. Dadkhah, R. Ferreira, A. Zohourian, R. Lu, and A. A. Ghorbani, "CICIoT2023: A real-time dataset and benchmark for large-scale attacks in IoT environment," *Sensors*, vol. 23, no. 13, p. 5941, 2023.
