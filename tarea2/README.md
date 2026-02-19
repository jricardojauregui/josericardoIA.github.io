# 📋 Actividad 1.2 — Regresión Lineal: Felicidad y GDP

**Autor:** José Ricardo Jáuregui Guevara | **Matrícula:** 608995  
**Fecha:** 26 de enero de 2026  
**Institución:** Universidad de Monterrey — Escuela de Ingeniería y Tecnologías

---

## 📌 Descripción de la Actividad

Esta actividad consiste en el ajuste y comparación de modelos de **regresión lineal** para explicar el nivel de felicidad de los países a partir de indicadores económicos y sociales. Se desarrollan dos modelos:

1. **Regresión lineal simple** — usando el GDP total como única variable predictora.
2. **Regresión lineal múltiple** — incorporando variables adicionales del World Happiness Report (GDP per cápita, apoyo social, esperanza de vida saludable y percepción de corrupción).

### Objetivos
- Explorar y visualizar la distribución de GDP y Felicidad entre países.
- Ajustar un modelo de regresión lineal simple y evaluar su desempeño (R²).
- Extender el dataset con variables del World Happiness Report.
- Ajustar un modelo de regresión lineal múltiple y compararlo con el simple.
- Concluir sobre la importancia de incorporar múltiples factores para explicar el bienestar.

---

## 🗃️ Bases de Datos

| Dataset | Descripción | Fuente |
|---|---|---|
| `A1_2_Felicidad_y_GDP.csv` | GDP total y nivel de felicidad para 141 países | Provisto por el curso |
| World Happiness Report (extensión) | GDP pc, apoyo social, esperanza de vida, corrupción | [kirenz/datasets en GitHub](https://raw.githubusercontent.com/kirenz/datasets/master/happy.csv) |

### Características del dataset principal

| Característica | Detalle |
|---|---|
| **Filas** | 141 (países) |
| **Columnas** | 3 (`Pais`, `Felicidad`, `GDP`) |
| **Tipos** | 1 objeto (string), 2 flotantes |
| **Valores nulos** | Ninguno |

---

## 📊 Hallazgos Principales

- El **GDP** presenta alta variabilidad entre países; la gran mayoría se concentra entre 0.0 y 0.3 (×10¹³).
- La **Felicidad** se distribuye de forma aproximadamente normal (en forma de campana).
- El modelo simple (GDP ~ Felicidad) obtiene un **R² ≈ 0.030**, lo que indica un ajuste muy bajo.
- Al incorporar GDP per cápita, apoyo social, esperanza de vida y corrupción, el **R² mejora a ≈ 0.686**, explicando cerca del 69% de la varianza en felicidad.
- La felicidad es un fenómeno **multifactorial** que no puede explicarse adecuadamente con una sola variable económica.

---

## 📂 Índice de Archivos

| Archivo | Descripción |
|---|---|
| [`Actividad1_2.ipynb`](./Actividad1_2.ipynb) | Notebook con el análisis completo |
| [`Actividad1_2.html`](./Actividad1_2.html) | Reporte en formato HTML (para GitHub Pages) |
| [`A1_2_Felicidad_y_GDP.csv`](./A1_2_Felicidad_y_GDP.csv) | Dataset principal utilizado |

> El dataset extendido del World Happiness Report se obtiene dinámicamente desde: https://raw.githubusercontent.com/kirenz/datasets/master/happy.csv

---

> *Actividad realizada con integridad académica.*
