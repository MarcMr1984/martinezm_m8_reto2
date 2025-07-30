# 📊 martinezm_m8_reto2 – Proyecto reproducible en Ciencia de Datos

Proyecto desarrollado para el **Reto 2** del módulo 8 del Máster Behavioral Data Science.  
Análisis técnico, visual e interactivo de la pobreza estructural en EE.UU. mediante datos abiertos del ACS S1701.

---

## 📌 Descripción general

Este proyecto busca identificar **patrones socioeconómicos de pobreza** a través de:
- Análisis multivariado por edad, género, raza, educación y empleo.
- Visualizaciones interactivas comparativas entre estados.
- Reproducibilidad completa con scripts documentados en R.

---

---

## 🎯 Objetivos del Proyecto

### Objetivo principal  
Desarrollar un análisis de Ciencia de Datos orientado a comprender y modelar el comportamiento de la pobreza estructural en EE.UU. mediante datos socioeconómicos del ACS S1701, generando insights accionables y visualizaciones reproducibles que apoyen decisiones informadas.

### Objetivos específicos  
- 📊 Explorar y limpiar el conjunto de datos para garantizar su calidad y adecuación al análisis.  
- 🔍 Identificar patrones relevantes de pobreza por variables como edad, género, raza, educación y empleo.  
- 🧠 Aplicar modelos de segmentación y regresión para explicar relaciones entre factores demográficos y pobreza.  
- 📈 Evaluar el rendimiento de los modelos con métricas cuantitativas y criterios de utilidad interpretativa.  
- 📑 Documentar el proceso completo siguiendo prácticas de reproducibilidad (scripts + dashboard interactivo).  
- 🧠 Interpretar los resultados y proponer recomendaciones basadas en datos para políticas públicas o investigación.

---

## 📁 Datos utilizados

Fuentes oficiales del **U.S. Census Bureau**, extraídas del programa **ACS 5-Year Estimates (2019–2023)**, tabla **S1701: Poverty Status in the Past 12 Months**.

| Archivo                                | Contenido principal                                          |
|----------------------------------------|--------------------------------------------------------------|
| `ACSST5Y2023.S1701-Data.csv`           | Datos estimados y márgenes de error por grupo poblacional   |
| `ACSST5Y2023.S1701-Column-Metadata.csv`| Diccionario técnico de las columnas (`_E`, `_M`, `_C`)       |
| `ACSST5Y2023.S1701-Table-Notes.txt`    | Notas metodológicas y definiciones del ACS                  |

Se ha generado un fichero limpio (`acs_clean.csv`) con variables renombradas para facilitar el análisis técnico y visual.

---

## 🔍 Diccionario de variables

Ejemplo de transformación automatizada desde `Column-Metadata.csv`:

| Código original      | Descripción legible                 |
|----------------------|-------------------------------------|
| `S1701_C03_002E`     | Pobreza infantil estimada (%)       |
| `S1701_C03_011M`     | Margen de error – pobreza mujeres   |
| `S1701_C03_026E`     | Personas con empleo por estado      |
| `S1701_C03_031E`     | % bajo el umbral de pobreza (total) |

Esta transformación se aplica mediante el script `code/rename_vars.R`.

---

## 🎯 Visualizaciones clave

| # | Tema                             | Técnica usada            | Insight obtenido                         |
|---|----------------------------------|---------------------------|------------------------------------------|
| 1️⃣ | Pobreza infantil por estado     | `geom_col()` horizontal  | PR y MS destacan con tasas elevadas      |
| 2️⃣ | Nivel educativo vs pobreza      | `pivot_longer()` + `boxplot` | Relación inversa clara                |
| 3️⃣ | Género y raza (con error bars) | `geom_errorbar()`        | Mujeres y minorías con mayor vulnerabilidad |
| 4️⃣ | Empleo ↔ pobreza                | `scatter` + `lm()`       | Correlación negativa notable              |

Los gráficos están integrados en el dashboard interactivo desarrollado con RMarkdown.

---

## 🎛️ Funcionalidades interactivas

- Filtros dinámicos: género, educación, raza.
- Tooltips con estimaciones + márgenes de error (`_E` y `_M`).
- Coordinación entre paneles por grupo poblacional.
- Selector geográfico por estado (`NAME`).

Diseño guiado por principios de percepción visual (Gestalt, Ware 2013) y codificación efectiva (Ribera 2023).

---

## 🧪 Tipología técnica de variables

| Tipo de dato         | Ejemplos                  | Uso visual                     |
|----------------------|---------------------------|--------------------------------|
| Categórico nominal   | `SEX`, `RACE`, `NAME`     | Colores, facetas por grupo     |
| Categórico ordinal   | Educación, edad           | Orden lógico, gradientes       |
| Numérico discreto    | Tamaño poblacional (`_C`) | Escala proporcional            |
| Numérico continuo    | % pobreza (`_E`)          | Ejes, tamaños, color cuantitativo |

---

## 📂 Estructura del repositorio

```
martinezm_m8_reto2/
├── data/
│   ├── ACSST5Y2023.S1701-Data.csv             # Datos originales del ACS
│   ├── ACSST5Y2023.S1701-Column-Metadata.csv  # Diccionario de columnas
│   ├── ACSST5Y2023.S1701-Table-Notes.txt      # Notas metodológicas
│   └── acs_clean.csv                          # Datos limpios para análisis
├── code/
│   ├── clean_data.R              # Limpieza y filtrado inicial
│   ├── rename_vars.R             # Renombrado automático desde metadata
│   └── analysis.R                # Script de visualización y modelado
├── dashboard/
│   └── dashboard.Rmd             # Dashboard interactivo en RMarkdown
├── report/
│   └── report.Rmd                # Informe técnico reproducible
├── presentation/
│   └── presentation.Rmd          # Presentación final del reto
└── README.md                     # Documento explicativo del proyecto
```


---

## 📜 Licencia

Distribuido bajo la **MIT License**.  
Puedes reutilizarlo libremente con fines educativos, científicos o analíticos.

---

## 🔗 Enlaces útiles

- [Documentación oficial ACS S1701](https://data.census.gov/table/ACSST5Y2023.S1701)
- [Guía RMarkdown](https://rmarkdown.rstudio.com/)
- [Licencia MIT](https://opensource.org/licenses/MIT)

---

## 🙋 Autoría

Proyecto desarrollado por **Marc Martínez** como parte del módulo 8 del *Máster en Behavioral Data Science* – Universidad de Barcelona.  
Profesores tutores: **Dr. David Leiva Ureña**, **Dra. Mireia Ribera Turró**

¿Feedback o sugerencias? ¡Bienvenidas!


