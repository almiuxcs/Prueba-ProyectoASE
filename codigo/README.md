# 📁 Código

## Orden de ejecución

Los notebooks están numerados y **deben ejecutarse en orden**. Cada uno genera los archivos que necesita el siguiente.

```
01_preprocesamiento.ipynb
        ↓ genera: datos/procesados/polizas_limpias.parquet
                          siniestros_limpios.parquet
                          dataset_modelado.parquet
02_analisis_exploratorio.ipynb
        ↓ genera: resultados/figuras/eda_*.png
                  resultados/tablas/estadisticas_descriptivas.csv
03_modelo_frecuencia.ipynb
        ↓ genera: resultados/modelos_guardados/glm_poisson.pkl
                  resultados/modelos_guardados/xgb_frecuencia.pkl
                  resultados/tablas/metricas_frecuencia.csv
04_modelo_severidad.ipynb
        ↓ genera: resultados/modelos_guardados/glm_gamma.pkl
                  resultados/tablas/metricas_severidad.csv
05_figuras_escrito.ipynb
        ↓ genera: escrito/figuras/*.pdf  (alta resolución para LaTeX)
```

---

## Descripción de cada notebook

### `01_limpieza/01_preprocesamiento.ipynb`
- Carga datos raw, inspección inicial (shape, dtypes, nulos)
- Tratamiento de valores faltantes y outliers
- Codificación de variables categóricas
- Construcción del dataset final de modelado
- **Semilla:** `random_state = 42`

### `02_eda/02_analisis_exploratorio.ipynb`
- Estadísticas descriptivas por variable
- Distribución de frecuencia (histogramas, Q-Q plots)
- Distribución de severidad (lognormal, gamma, Pareto)
- Correlaciones y análisis bivariado
- Mapa de calor por región geográfica

### `03_modelos/03_modelo_frecuencia.ipynb`
- Modelo GLM con distribución Poisson (liga log)
- XGBoost para frecuencia
- Validación cruzada 5-fold
- Métricas: AIC, BIC, RMSE, MAE, Deviance

### `03_modelos/04_modelo_severidad.ipynb`
- Modelo GLM con distribución Gamma (liga log)
- Prueba de ajuste: Kolmogorov-Smirnov, Anderson-Darling
- Comparación lognormal vs Gamma vs Pareto generalizada
- Prima pura = E[N] × E[S]

### `04_visualizaciones/05_figuras_escrito.ipynb`
- Regenera todas las figuras en formato PDF/EPS para LaTeX
- Paleta de colores consistente con el escrito
- Tamaños de figura optimizados para columna de artículo

---

## Convenciones de código

- Todas las funciones auxiliares están documentadas con docstrings
- Las semillas aleatorias se fijan con `np.random.seed(42)` y `random_state=42`
- Los paths se manejan con `pathlib.Path` para compatibilidad multiplataforma
- Los warnings se suprimen solo en las celdas de salida final, no en exploración
