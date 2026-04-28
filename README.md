# 📊 Predicción de Siniestralidad en Seguros de Gastos Médicos Mayores

[![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![LaTeX](https://img.shields.io/badge/LaTeX-Escrito-008080?style=flat&logo=latex&logoColor=white)](https://www.latex-project.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Estado](https://img.shields.io/badge/Estado-En%20progreso-blue)]()

> **Proyecto de Aplicación en Seguros y Estadística (ASE)**  
> Universidad Iberoamericana Ciudad de México · Licenciatura en Actuaría  
> Semestre Primavera 2025

---

## 🎯 Descripción

Este proyecto analiza y modela la **frecuencia y severidad de siniestros** en una cartera de seguros de Gastos Médicos Mayores (GMM) usando técnicas actuariales clásicas y modelos de machine learning. El objetivo es construir un modelo predictivo que apoye la tarificación y el cálculo de reservas.

**Pregunta de investigación:**  
¿Pueden los modelos GLM y gradient boosting mejorar la estimación de la prima pura respecto a los métodos actuariales tradicionales para carteras de GMM en México?

---

## 🗂️ Estructura del repositorio

```
ase-proyecto-ejemplo/
│
├── 📄 README.md                    ← Este archivo
├── 📄 requirements.txt             ← Dependencias Python
├── 📄 environment.yml              ← Entorno Conda (alternativo)
├── 📄 .gitignore                   ← Archivos excluidos del repo
├── 📄 LICENSE
│
├── 📁 datos/
│   ├── raw/                        ← Datos originales sin modificar
│   ├── procesados/                 ← Datos limpios listos para análisis
│   └── externos/                   ← Catálogos, tablas de referencia
│
├── 📁 codigo/
│   ├── 01_limpieza/                ← Scripts de limpieza y preprocesamiento
│   ├── 02_eda/                     ← Análisis exploratorio
│   ├── 03_modelos/                 ← Entrenamiento y evaluación de modelos
│   └── 04_visualizaciones/         ← Figuras finales para el escrito
│
├── 📁 escrito/
│
├── 📁 presentaciones/
│   ├── avance1/                    ← Primera presentación de avance
│   ├── avance2/                    ← Segunda presentación de avance
│   └── final/                      ← Presentación final
│
├── 📁 resultados/
│   ├── figuras/                    ← Gráficas generadas por los scripts
│   ├── tablas/                     ← Resultados numéricos en CSV/LaTeX
│   └── modelos_guardados/          ← Modelos serializados (.pkl, .joblib)
```

---

## 🚀 Cómo reproducir este proyecto

### Requisitos previos

- Python 3.10+
- Conda o pip
- LaTeX (TeX Live o MiKTeX) para compilar el escrito

### 1. Clonar el repositorio

```bash
git clone https://github.com/usuario/ase-siniestralidad-gmm.git
cd ase-siniestralidad-gmm
```

### 2. Instalar dependencias

```bash
# Opción A: pip
pip install -r requirements.txt

# Opción B: Conda
conda env create -f environment.yml
conda activate ase-gmm
```

### 3. Ejecutar los notebooks en orden

```bash
# 1. Limpieza de datos
jupyter notebook codigo/01_limpieza/01_preprocesamiento.ipynb

# 2. Análisis exploratorio
jupyter notebook codigo/02_eda/02_analisis_exploratorio.ipynb

# 3. Modelos
jupyter notebook codigo/03_modelos/03_modelo_frecuencia.ipynb
jupyter notebook codigo/03_modelos/04_modelo_severidad.ipynb

# 4. Figuras finales
jupyter notebook codigo/04_visualizaciones/05_figuras_escrito.ipynb
```

### 4. Compilar el escrito (LaTeX)

```bash
cd escrito
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

---

## 📈 Resultados principales

| Modelo | AIC | RMSE (Frecuencia) | RMSE (Severidad) |
|--------|-----|-------------------|------------------|
| GLM Poisson | 1842.3 | 0.142 | — |
| GLM Gamma | — | — | 4,230 |
| XGBoost | — | 0.118 | 3,890 |
| Modelo compuesto | — | — | **3,650** |

> Los resultados detallados se encuentran en `resultados/tablas/` y en la Sección 5 del escrito.

---

## 📚 Tecnologías utilizadas

| Categoría | Herramienta |
|-----------|-------------|
| Lenguaje | Python 3.10 |
| Análisis | pandas, numpy, scipy |
| Modelos | scikit-learn, statsmodels, xgboost |
| Visualización | matplotlib, seaborn, plotly |
| Escrito | LaTeX (clase article, biblatex) |
| Presentaciones | Beamer (LaTeX) |
| Control de versiones | Git + GitHub |

---

## 👤 Autores

| Nombre | Correo | Rol |
|--------|--------|-----|
| Ana García López | ana.garcia@ibero.mx | Modelado estadístico |
| Carlos Mendoza Ruiz | carlos.mendoza@ibero.mx | Limpieza y EDA |
| Sofía Torres Vega | sofia.torres@ibero.mx | Escrito y presentaciones |

**Asesora:** Dra. [Nombre] · Departamento de Actuaría · Universidad Iberoamericana

---

## 📅 Cronograma

- [x] Semana 1–2: Obtención y limpieza de datos
- [x] Semana 3–4: Análisis exploratorio
- [x] Semana 5–6: Modelado de frecuencia
- [ ] Semana 7–8: Modelado de severidad
- [ ] Semana 9–10: Modelo compuesto y tarificación
- [ ] Semana 11–12: Escritura final y presentación

---

## 📄 Licencia

Este proyecto está bajo la licencia MIT. Ver el archivo [LICENSE](LICENSE) para más detalles.

---

## 📎 Referencias clave

- Klugman, S. A., Panjer, H. H., & Willmot, G. E. (2012). *Loss Models: From Data to Decisions* (4th ed.). Wiley.
- De Jong, P., & Heller, G. Z. (2008). *Generalized Linear Models for Insurance Data*. Cambridge.
- CNSF (2023). *Estadísticas del Sector Asegurador México*. Comisión Nacional de Seguros y Fianzas.
