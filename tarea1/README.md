# 📋 Actividad 1.1 — Exploración Inicial de Datos: Obesidad

**Autor:** José Ricardo Jáuregui Guevara | **Matrícula:** 608995

---

## 📌 Descripción de la Actividad

Esta actividad consiste en una **exploración inicial (EDA)** de un dataset relacionado con el sobrepeso y la obesidad en personas. Se analizan las características del dataset, la distribución de la variable dependiente, se propone una nueva variable relevante, se define y calcula una variable derivada de interés (BMI) y se realiza un análisis gráfico sobre una subpoblación específica (hombres).

### Objetivos
- Identificar el tipo y estructura de las variables del dataset.
- Analizar la distribución de la variable dependiente `NivelDeObesidad`.
- Proponer una variable adicional que enriquezca el estudio.
- Calcular el BMI como variable derivada de interés para inferencia.
- Visualizar la relación BMI vs Edad en la subpoblación masculina.

---

## 🗃️ Base de Datos

| Característica | Detalle |
|---|---|
| **Nombre** | Obesidad |
| **Fuente** | Dataset provisto por el curso |
| **Archivo** | `A1_1_Obesidad.csv` |
| **Filas** | 2,111 |
| **Columnas** | 10 |
| **Valores nulos** | Ninguno |

### Variables

**Numéricas (5):** `Edad`, `Estatura`, `Peso`, `ComeVegetales`, `ConsumoDeAgua`

**Categóricas (5):** `Sexo`, `FamiliarConSobrepeso`, `ComeMuchasCalorias`, `Fumador`, `NivelDeObesidad`

**Variable dependiente:** `NivelDeObesidad` — categoriza el nivel de obesidad de cada persona.

**Variable derivada calculada:** `BMI` (Índice de Masa Corporal) = Peso / Estatura²

---

## 📊 Hallazgos Principales

- Las clases de `NivelDeObesidad` están **relativamente balanceadas**, con `Obesity_Type_I` como la más frecuente e `Insufficient_Weight` como la menos frecuente. Esto es positivo para modelos de clasificación.
- El **BMI** en el dataset va desde ~13 hasta ~51. La moda es **26.67** y la mediana es **28.72**, con una distribución **multimodal**.
- En la subpoblación masculina, se observa una **leve tendencia positiva** entre edad y BMI: a mayor edad, tiende a aumentar el BMI.
- Se propone la variable `CantidadHorasEjercicio` como mejora al diseño del estudio, dado que la actividad física es un factor clave relacionado con el sobrepeso.

---

## 📂 Índice de Archivos

| Archivo | Descripción |
|---|---|
| [`Actividad1_1.ipynb`](./Actividad1_1.ipynb) | Notebook con el análisis completo y visualizaciones |
| [`Actividad1_1.html`](./Actividad1_1.html) | Reporte en formato HTML (renderizable en GitHub Pages) |
| [`A1_1_Obesidad.csv`](./A1_1_Obesidad.csv) | Base de datos utilizada |

---

> *Actividad realizada con integridad académica.*
