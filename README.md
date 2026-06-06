# Predicción de Aprobación de Créditos Bancarios mediante Modelos de Aprendizaje Automático

Proyecto de aula del curso **Modelos y Simulación II** — Universidad de Antioquia.

Análisis comparativo de siete modelos de aprendizaje automático aplicados a la
predicción de aprobación de créditos bancarios, utilizando el conjunto de datos
*Loan Prediction Problem*. Incluye preprocesamiento, ajuste de hiperparámetros,
evaluación con validación cruzada estratificada y reducción de dimensión (PCA y UMAP).

## Autores

- Sara Galván Ortega — sara.galvan@udea.edu.co
- Juan Pablo Ramos Vélez — juanp.ramos@udea.edu.co
- David Arango Pineda — david.arango6@udea.edu.co

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `Informe_final.pdf` | Reporte del proyecto en formato IEEE. |
| `entregable_final.ipynb` | Notebook reproducible con todo el análisis. |
| `train.csv` | Datos de entrenamiento (incluye la variable objetivo). |
| `test.csv` | Datos de prueba de Kaggle (sin variable objetivo). |

## Conjunto de datos

Se utiliza el *Loan Prediction Problem* (614 registros, 12 variables predictoras y
una variable objetivo `Loan_Status`), disponible públicamente en Kaggle:
https://www.kaggle.com/datasets/altruistdelhite04/loan-prediction-problem-dataset

> **Nota:** el archivo `test.csv` de Kaggle no incluye la variable objetivo, por lo
> que la evaluación de desempeño se realiza particionando `train.csv`
> (80 % desarrollo / 20 % prueba).

## Requisitos

El notebook está diseñado para ejecutarse en **Google Colab** (recomendado) o en un
entorno local con Python 3.10+. Dependencias principales:

pandas, numpy, matplotlib, seaborn, scikit-learn, xgboost, umap-learn

En Colab, las librerías que no vienen por defecto se instalan con:

```python
!pip install umap-learn xgboost -q
```

## Cómo reproducir los resultados

1. Abrir `entregable_final.ipynb` en Google Colab.
2. Subir el archivo `train.csv` al entorno de ejecución (o ajustar la celda de carga
   de datos según corresponda).
3. Ejecutar el notebook completo con **Entorno de ejecución → Ejecutar todo**.

El notebook reproduce todas las tablas y figuras incluidas en el informe: comparación
de modelos, curvas ROC, matriz de confusión y los resultados de PCA y UMAP.

## Resumen de resultados

- Se compararon siete modelos: Regresión Logística, K-Nearest Neighbors,
  Árbol de Decisión, Random Forest, XGBoost, SVM y una red neuronal (MLP).
- **SVM** obtuvo el mejor desempeño (F1 = 0.903 en prueba), aunque las diferencias
  entre los modelos no fueron estadísticamente significativas.
- La reducción de dimensión con **PCA** conservó el desempeño del modelo completo
  utilizando un 21.4 % menos de variables; **UMAP** degradó el desempeño.
- La variable `Credit_History` concentra la mayor capacidad discriminativa del problema.

El reporte completo con la metodología, los resultados y la discusión se encuentra en
`Informe_final.pdf`.

## Video exposición
https://drive.google.com/file/d/1DnhWS6tdj5I_SyGueCnmis9dxcc1CxvX/view?usp=sharing

