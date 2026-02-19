# 📋 Actividad 1.3 — Regresión Lineal Múltiple: Predicción de Calificaciones

**Autor:** José Ricardo Jáuregui Guevara | **Matrícula:** 608995  
**Institución:** Universidad de Monterrey — Escuela de Ingeniería y Tecnologías

---

## 📌 Descripción de la Actividad

Esta actividad consiste en construir y evaluar un **modelo de regresión lineal múltiple** para predecir la calificación final (G3) de estudiantes a partir de variables académicas, demográficas y de hábitos. El análisis incluye preprocesamiento de variables categóricas, selección de características basada en significancia estadística (p-valor), evaluación del modelo con métricas de error y validación con conjunto de prueba.

### Objetivos
- Explorar y preprocesar el dataset de calificaciones (codificación de variables categóricas).
- Analizar la matriz de correlaciones para identificar relaciones entre variables.
- Seleccionar las variables más significativas mediante `statsmodels` OLS y p-valores.
- Entrenar un modelo de regresión lineal múltiple con scikit-learn (split 80/20).
- Evaluar el modelo con R², MSE, RMSE y MAPE en entrenamiento y prueba.
- Interpretar los coeficientes y realizar predicciones con el modelo final.

---

## 🗃️ Base de Datos

| Característica | Detalle |
|---|---|
| **Nombre** | Student Performance (Calificaciones) |
| **Archivo** | `A1_3_Calificaciones.csv` |
| **Fuente** | UCI Machine Learning Repository |
| **Referencia** | ICS (2014). *Student Performance*. https://archive.ics.uci.edu/dataset/320/student+performance |
| **Filas** | 395 |
| **Columnas** | 10 |

### Variables del Dataset

| Variable | Tipo | Descripción |
|---|---|---|
| `Escuela` | Categórica | Escuela del estudiante (GP / MS) |
| `Sexo` | Categórica | Género (F / M) |
| `Edad` | Numérica | Edad del estudiante |
| `HorasDeEstudio` | Numérica | Horas de estudio semanales |
| `Reprobadas` | Numérica | Número de materias reprobadas |
| `Internet` | Categórica | Acceso a internet (yes / no) |
| `Faltas` | Numérica | Número de faltas |
| `G1` | Numérica | Calificación del primer período (0–20) |
| `G2` | Numérica | Calificación del segundo período (0–20) |
| `G3` ⭐ | Numérica | **Variable objetivo:** calificación final (0–20) |

---

## 🔧 Metodología

1. **Preprocesamiento:** Label Encoding para `Sexo`, `Escuela` e `Internet`.
2. **Correlación:** Matriz de correlaciones para identificar relaciones y multicolinealidad.
3. **Selección de variables:** Modelo OLS completo con `statsmodels`; se descartan variables con p-valor > 0.05.
4. **Variables finales seleccionadas:** `G2`, `Reprobadas`, `Faltas`, `Sexo_num`.
5. **Entrenamiento:** Split 80/20 con `random_state=0`.
6. **Evaluación:** R², MSE, RMSE, MAPE en train y test.

---

## 📊 Resultados Principales

| Métrica | Entrenamiento | Prueba |
|---|---|---|
| R² | 0.83 | 0.80 |
| RMSE | — | 2.36 |
| Diferencia R² | — | 3.58% |

**Ecuación del modelo:**  
`G3 = -1.21 + 0.05·Faltas + (-0.33)·Reprobadas + 1.07·G2 + 0.21·Sexo`

**Conclusión:** G2 es la variable más influyente para predecir G3. El historial académico previo es el mejor predictor del desempeño final. El modelo no presenta overfitting significativo (diferencia R² < 4%).

---

## 📂 Índice de Archivos

| Archivo | Descripción |
|---|---|
| [`Actividad1_3.ipynb`](./Actividad1_3.ipynb) | Notebook con el análisis completo |
| [`Actividad1_3.html`](./Actividad1_3.html) | Reporte en formato HTML (para GitHub Pages) |
| [`A1_3_Calificaciones.csv`](./A1_3_Calificaciones.csv) | Dataset utilizado |

---

> *Actividad realizada con integridad académica.*  
> **Referencia:** ICS (2014). Student Performance. UCI ML Repository. https://archive.ics.uci.edu/dataset/320/student+performance
