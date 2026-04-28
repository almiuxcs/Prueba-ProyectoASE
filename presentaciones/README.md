# 📁 Presentaciones

## Estructura

Cada carpeta de avance contiene:
- `slides.pdf` — PDF compilado (el que se presenta)
- `slides.tex` — Fuente LaTeX Beamer
- `figuras/` — Imágenes usadas en las diapositivas

## Avances

### `avance1/` — Semana 4
**Tema:** Planteamiento del problema, descripción de datos y EDA inicial  
**Diapositivas:** 12  
**Presentado:** [fecha]

Contenido:
- Motivación y pregunta de investigación
- Descripción de la cartera GMM
- Estadísticas descriptivas univariadas
- Distribución empírica de frecuencia y severidad
- Plan de trabajo

---

### `avance2/` — Semana 8
**Tema:** Resultados del modelado de frecuencia  
**Diapositivas:** 15  
**Presentado:** [fecha]

Contenido:
- Recordatorio del marco teórico GLM Poisson
- Selección de variables (AIC stepwise)
- Diagnóstico del modelo: residuales, sobredispersión
- Comparación GLM vs XGBoost en validación cruzada
- Próximos pasos: modelo de severidad

---

### `final/` — Semana 12
**Tema:** Resultados completos y conclusiones  
**Diapositivas:** 20  
**Presentado:** [fecha]

Contenido:
- Resumen ejecutivo del proyecto
- Modelo compuesto: frecuencia × severidad
- Tarificación relativa por perfil de riesgo
- Comparación final GLM vs XGBoost
- Limitaciones y trabajo futuro
- Conclusiones

---

## Plantilla Beamer

Se usa la clase `beamer` con el tema `Madrid` modificado. Para compilar:

```bash
cd avance1
pdflatex slides.tex
bibtex slides
pdflatex slides.tex
```
