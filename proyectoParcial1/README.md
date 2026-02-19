# 🏠 Proyecto Parcial 1 — Determinantes del Ingreso en Hogares Mexicanos

**Autor:** José Ricardo Jáuregui Guevara | **Matrícula:** 608995  
**Institución:** Universidad de Monterrey — Escuela de Ingeniería y Tecnologías  
**Fecha:** Enero–Febrero 2026

---

## 📌 Descripción del Proyecto

Este proyecto analiza los **determinantes socioeconómicos del ingreso corriente total** de los hogares mexicanos (`ing_cor`) utilizando datos de la **Encuesta Nacional de Ingresos y Gastos de los Hogares (ENIGH) 2014** del INEGI.

Se aplica un flujo metodológico completo de ciencia de datos: exploración, limpieza, selección de variables con tres métodos distintos (backward, forward, stepwise), construcción y comparación de tres modelos predictivos, evaluación de desempeño e inferencia estadística con errores robustos.

### Objetivo
Identificar qué características del hogar están estadísticamente asociadas con el nivel de ingreso y construir un modelo predictivo que capture esas relaciones.

---

## 🗃️ Base de Datos

| Característica | Detalle |
|---|---|
| **Nombre** | ENIGH 2014 — Principales variables por hogar |
| **Fuente** | INEGI (Instituto Nacional de Estadística y Geografía) |
| **Referencia** | https://www.inegi.org.mx/programas/enigh/nc/2014/ |
| **Filas** | 58,125 hogares |
| **Columnas** | 59 variables |
| **Variable objetivo** | `ing_cor` → transformada a `log_ing_cor` |

> ⚠️ El dataset original pesa varios MB. Descárgalo directamente desde el sitio del INEGI en el link de arriba (`mcs_concentrado_2014_concil_2010.csv`).

---

## 🔧 Metodología

1. **Exploración inicial** — Revisión de tipos, nulos, estadísticas descriptivas y distribuciones.
2. **Limpieza** — Eliminación de IDs, verificación de nulos, transformación logarítmica de `ing_cor`.
3. **Selección de variables** — Tres métodos: *Backward Elimination*, *Forward Selection*, *Stepwise*. Se adopta el **núcleo estable** (variables seleccionadas por los tres métodos).
4. **Modelos construidos:**
   - Regresión Lineal Múltiple (OLS)
   - Random Forest base
   - Random Forest optimizado (RandomizedSearchCV, 5-fold CV)
5. **Evaluación** — R², RMSE, MAE, brecha train/test.
6. **Inferencia** — OLS con errores robustos HC3, intervalos de confianza, p-valores.
7. **Análisis What-if** — Simulación de escenarios hipotéticos con el RF optimizado.

---

## 📊 Variables Finales Seleccionadas (Núcleo Estable)

`clase_hog`, `edad_jefe`, `educa_jefe`, `est_socio`, `mayores`, `ocupados`, `p12_64`, `percep_ing`, `sexo_jefe`, `tam_loc`

---

## 📈 Resultados Principales

| Modelo | R² Train | R² Test | Brecha | RMSE Test | MAE Test |
|---|---|---|---|---|---|
| Regresión Lineal | 0.4407 | 0.4387 | 0.0020 | 0.6719 | 0.4997 |
| RF Base | 0.8494 | 0.3596 | 0.4898 | 0.7176 | 0.5331 |
| **RF Optimizado** ✅ | **0.5386** | **0.4676** | **0.0710** | **0.6543** | **0.4843** |

**Modelo ganador:** Random Forest Optimizado (`max_depth=10`, `min_samples_leaf=2`, `min_samples_split=14`, `n_estimators=1000`).

### Hallazgos clave
- **`educa_jefe`** es el predictor más importante en el RF (importancia 0.33): mayor educación → mayor ingreso.
- **`est_socio`** tiene el mayor efecto lineal en OLS (β=0.256, equivale a +29.2% en ingreso).
- Hogares encabezados por **mujeres** ganan ~5.1% menos; hogares en **localidades pequeñas** ganan ~7.3% menos.

---

## 📂 Índice de Archivos

| Archivo | Descripción |
|---|---|
| [`Proyecto1.ipynb`](./Proyecto1.ipynb) | Notebook con el análisis completo |
| [`Proyecto1.html`](./Proyecto1.html) | Reporte HTML (renderizable en GitHub Pages) |
| Dataset | Descargable en https://www.inegi.org.mx/programas/enigh/nc/2014/ |

---

> *Proyecto realizado con integridad académica.*

### Referencias principales
- INEGI (2014). *ENIGH 2014*. https://www.inegi.org.mx/programas/enigh/nc/2014/
- Pedregosa et al. (2011). *Scikit-learn*. JMLR.
- Seabold & Perktold (2010). *Statsmodels*. https://www.statsmodels.org
