# 📁 Datos

## Descripción de archivos

### `raw/` — Datos originales
> ⚠️ **No se suben al repositorio** (ver `.gitignore`). Solicitar acceso a los autores.

| Archivo | Descripción | Fuente | Registros | Peso |
|---------|-------------|--------|-----------|------|
| `cartera_gmm_2019_2023.csv` | Pólizas activas GMM con variables de riesgo | Simulado (basado en estructura CNSF) | ~15,000 | ~8 MB |
| `siniestros_gmm_2019_2023.csv` | Registro histórico de reclamaciones | Simulado | ~42,000 | ~12 MB |
| `catalogo_diagnosticos_cie10.xlsx` | Catálogo CIE-10 para clasificar diagnósticos | IMSS / OMS | 10,000+ | ~2 MB |

### `raw/muestra_100registros.csv`
Muestra anonimizada de 100 registros para verificar que el código corre correctamente **sin necesidad de los datos completos**.

### `procesados/` — Datos limpios
Generados por `codigo/01_limpieza/01_preprocesamiento.ipynb`. También excluidos del repo por tamaño.

| Archivo | Contenido |
|---------|-----------|
| `polizas_limpias.parquet` | Cartera sin duplicados, variables codificadas |
| `siniestros_limpios.parquet` | Reclamaciones con indicador de frecuencia y monto normalizado |
| `dataset_modelado.parquet` | Join final polizas + siniestros, listo para modelado |

### `externos/` — Tablas de referencia (sí en el repo)

| Archivo | Descripción |
|---------|-------------|
| `factor_edad_cnsf.csv` | Factores de ajuste por edad publicados por CNSF |
| `inflacion_medica_banxico.csv` | Índice de inflación médica 2015–2024 (Banxico) |

---

## Variables principales del dataset

| Variable | Tipo | Descripción |
|----------|------|-------------|
| `id_poliza` | str | Identificador único de póliza |
| `edad_contratante` | int | Edad al momento de contratación |
| `sexo` | cat | M / F |
| `suma_asegurada` | float | Suma asegurada en MXN |
| `deducible` | float | Deducible pactado en MXN |
| `coaseguro` | float | Porcentaje de coaseguro |
| `region` | cat | Región CNSF (Norte, Centro, Sur, CDMX) |
| `n_siniestros` | int | Número de reclamaciones en el periodo |
| `monto_total_siniestros` | float | Monto total reclamado en MXN |

---

## Notas de privacidad
Los datos originales son **simulados** para fines académicos con una estructura consistente con carteras reales de GMM en México. No contienen información personal real.
