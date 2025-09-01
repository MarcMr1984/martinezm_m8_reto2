# 📊 martinezm_m8_reto2 – Proyecto reproducible en Ciencia de Datos

Proyecto desarrollado para el **Reto 2** del módulo 8 del Máster Behavioral Data Science.  

Análisis técnico, visual e interactivo de la evolución de la pobreza en EE.UU. entre 2016 y 2023, con especial atención a las diferencias entre **subgrupos sociales** y **estados**, utilizando datos abiertos del ACS S1701.

---

### 📌 Descripción general

<div style="text-align: justify"> 
Este proyecto presenta un estudio detallado de la pobreza en Estados Unidos, basado en datos del American Community Survey (ACS), tabla S1701.  

Se analizan **patrones persistentes**, **brechas estructurales** y **dinámicas territoriales** que afectan la distribución de la pobreza, con énfasis en variables como edad, género, etnia, educación y empleo.

A través de indicadores clave (KPIs), estimaciones robustas y visualizaciones interactivas, se ofrece una herramienta útil para investigadores, responsables de políticas públicas y cualquier persona interesada en comprender las desigualdades socioeconómicas en el país.
</div>

---

### 🎯 Objetivos del Proyecto

#### Objetivo principal  
Desarrollar un análisis reproducible y riguroso sobre la evolución de la pobreza estructural en EE.UU. entre 2016 y 2023, identificando patrones sociales y territoriales que permitan generar insights accionables.

#### Objetivos específicos  
- 📊 Explorar y limpiar los datos del ACS para garantizar su calidad y consistencia.  
- 🔍 Identificar diferencias significativas entre subgrupos sociales y estados.  
- 🧠 Analizar relaciones entre factores demográficos y pobreza mediante visualización multivariada.  
- 📈 Generar estimaciones robustas y KPIs que permitan evaluar tendencias y desigualdades.  
- 📑 Documentar el proceso completo siguiendo prácticas de reproducibilidad (scripts + dashboard interactivo).  
- 🧭 Proponer recomendaciones basadas en datos para investigación aplicada y diseño de políticas públicas.

---

### 📁 Datos utilizados

Fuentes oficiales del **U.S. Census Bureau**, extraídas del programa **ACS 1-Year Estimates (2016–2023)**, tabla **S1701: Poverty Status in the Past 12 Months**.

| Archivo                                        | Contenido principal                                                |
|------------------------------------------------|--------------------------------------------------------------------|
| `ACSSTTY2016_51701-2025-08-04T150306_2016.csv` | Datos originales del ACS para el año 2016                          |
| `ACSSTTY2017_51701-2025-08-04T150322_2017.csv` | Datos originales del ACS para el año 2017                          |
| `ACSSTTY2018_51701-2025-08-04T150338_2018.csv` | Datos originales del ACS para el año 2018                          |
| `ACSSTTY2019_51701-2025-08-04T150354_2019.csv` | Datos originales del ACS para el año 2019                          |
| `ACSSTTY2021_51701-2025-08-04T150427_2021.csv` | Datos originales del ACS para el año 2021                          |
| `ACSSTTY2022_51701-2025-08-04T150442_2022.csv` | Datos originales del ACS para el año 2022                          |
| `ACSSTTY2023_51701-2025-08-04T104942_2023.csv` | Datos originales del ACS para el año 2023                          |
| `df_pobreza_con_estimacion.csv`                | Dataset consolidado con estimaciones de pobreza añadidas           |
| `df_pobreza_limpio.csv`                        | Dataset final limpio y estructurado para análisis y visualización


---

### 🔍 Diccionario de variables

El dataset final incluye variables limpias y recodificadas, derivadas de los archivos originales del ACS. La estructura se ha generado mediante un proceso de consolidación, limpieza y estimación robusta, implementado en los scripts clean_data.R, estimate_2020.R y rename_vars.R.

| Variable               | Tipo de dato         | Descripción                                                             |
|------------------------|----------------------|-------------------------------------------------------------------------|
| `Fecha`                | Temporal (Date)      | Año de referencia del dato, en formato `YYYY-MM-DD`                     |
| `Estado`               | Categórico nominal   | Estado de EE.UU. al que pertenece el dato                               |
| `Grupo_social`         | Categórico nominal   | Subgrupo poblacional (e.g., "Menores de edad", "Desempleados")          |
| `Tematica`             | Categórico jerárquico| Categoría temática: Edad, Sexo, Etnia, Educación, Empleo                |
| `Total_poblacion`      | Numérico (integer)   | Población total del grupo                                               |
| `Bajo_umbral_pobreza`  | Numérico (integer)   | Número de personas bajo el umbral de pobreza                            |
| `Porcentaje_pobreza`   | Numérico (double)    | Proporción de pobreza (0–1), transformada a porcentaje                  |
| `Origen_dato`          | Categórico nominal   | Fuente del dato: `"Original"` o `"Estimado"` (solo para el año 2020)    |


---

### 📂 Estructura del repositorio

```
martinezm_m8_reto2/
├── data/
│   ├── ACSSTTY2016_51701-2025-08-04T150306_2016.csv   # Datos originales del ACS 2016
│   ├── ACSSTTY2017_51701-2025-08-04T150322_2017.csv   # Datos originales del ACS 2017
│   ├── ACSSTTY2018_51701-2025-08-04T150338_2018.csv   # Datos originales del ACS 2018
│   ├── ACSSTTY2019_51701-2025-08-04T150354_2019.csv   # Datos originales del ACS 2019
│   ├── ACSSTTY2021_51701-2025-08-04T150427_2021.csv   # Datos originales del ACS 2021
│   ├── ACSSTTY2022_51701-2025-08-04T150442_2022.csv   # Datos originales del ACS 2022
│   ├── ACSSTTY2023_51701-2025-08-04T104942_2023.csv   # Datos originales del ACS 2023
│   ├── df_pobreza_limpio.csv                          # Dataset limpio consolidado para análisis
│   └── df_pobreza_con_estimacion.csv                  # Dataset con estimaciones de pobreza añadidas para el año 2020
├── dashboard/
│   └── dashboard.Rmd                                   # Script en RMarkdown para generar el dashboard interactivo
├── informe/
│   ├── codigo_informe_html.Rmd                         # Código fuente del informe en formato HTML
│   ├── codigo_informe_html.html                        # Informe generado en HTML
│   ├── codigo_informe_pdf.Rmd                          # Código fuente del informe en formato PDF
│   ├── codigo_informe.pdf                              # Informe generado en PDF
│   └── informe.pdf                                     # Versión final del informe técnico
├── presentacion/
│   ├── presentacion.Rmd                                # Código fuente de la presentación final en RMarkdown
│   └── presentacion.html                               # Presentación renderizada en formato HTML
├── .gitignore                                          # Exclusión de archivos innecesarios en control de versiones
├── LICENSE                                             # Licencia del proyecto
├── martinezm_m8_reto2.Rproj                            # Archivo de proyecto RStudio
└── README.md                                           # Documento explicativo del proyecto

```

---

### 📊 Visualización y Dashboard

El dashboard incluye:
- Filtros dinámicos por estado y temática.
- KPIs clave: % pobreza actual, crecimiento anual, evolución 5 años.
- Gráficos: líneas, barras, circular, boxplots, dispersión.
- Codificación visual: color por temática, forma por año estimado, tooltips explicativos.
- Interacción cruzada entre gráficos (linked brushing) y hover para valores exactos.

Diseñado con `flexdashboard`, `ggplot2`, `plotly` y `dplyr`.

---


### 📄 Informe técnico reproducible

<div style="text-align: justify"> 
Generado con `knitr` y `RMarkdown`, este informe presenta un análisis detallado y reproducible sobre la evolución de la pobreza en EE.UU. entre 2016 y 2023, con foco en subgrupos sociales y estados. Incluye:

- 📋 **Tabla resumen** por estado y grupo social, con indicadores clave como población total, bajo umbral de pobreza y porcentaje de pobreza.
- 📈 **Gráficos de evolución temporal** por grupo social, con estimaciones robustas para el año 2020 en ausencia de datos oficiales.
- 🧠 **Texto explicativo** con código embebido (`r` inline y chunks), que documenta cada paso del procesamiento, modelado y visualización.
- 📊 **Visualizaciones exploratorias** como histogramas, boxplots, gráficos de dispersión y circulares, que permiten detectar patrones, outliers y relaciones estructurales.
- 🧮 **Indicadores clave (KPIs)** sobre pobreza actual, variación anual y evolución en cinco años, útiles para el monitoreo y evaluación de políticas públicas.
- 🎨 **Codificación visual personalizada** mediante un vector de colores temático, que mejora la legibilidad y coherencia del dashboard interactivo.
</div>

---

### 🖥️ Presentación final

Presentación en `RMarkdown` con narrativa visual y enfoque estructural:

- Visualización de KPIs nacionales sobre evolución de la pobreza (2016–2023).

- Análisis comparativo por grupo social: educación, empleo, edad, etnia y sexo.

- Identificación de patrones persistentes y brechas estructurales.

- Gráficos temáticos: evolución temporal, distribución absoluta, outliers territoriales.

- Interpretaciones guiadas con código reproducible y enfoque orientado a políticas públicas.

---

### 💻 Reproducibilidad

Todo el análisis está documentado con scripts en R:

- Estructura modular por funciones y fases.
- Dashboard interactivo creado con `flexdashboard` y `plotly`.
- Control de versiones mediante Git.

---

### 🧪 Entorno de ejecución

- **Versión de R**: 4.3.1  
- **IDE utilizado**: RStudio

### 📦 Principales paquetes utilizados

| Paquete        | Función principal                                 |
|----------------|---------------------------------------------------|
| `tidyverse`    | Manipulación de datos, visualización y modelado  |
| `lubridate`    | Manejo de fechas y tiempos                        |
| `ggplot2`      | Visualización estática avanzada                   |
| `plotly`       | Visualización interactiva                         |
| `flexdashboard`| Creación de dashboards interactivos               |
| `knitr`        | Generación de informes reproducibles              |
| `rmarkdown`    | Documentación y presentación en formato dinámico  |

> Todos los paquetes están documentados en el archivo `renv.lock` para facilitar la instalación reproducible del entorno.

---

### 📜 Licencia

Distribuido bajo la **MIT License**.  
Puedes reutilizarlo libremente con fines educativos, científicos o analíticos.

---

## 🔗 Enlaces útiles

- [Documentación oficial ACS S1701](https://data.census.gov/table/ACSST5Y2023.S1701)  
- [Guía RMarkdown](https://rmarkdown.rstudio.com/)  
- [Licencia MIT](https://opensource.org/licenses/MIT)

---

### 🙋 Autoría

Proyecto desarrollado por **Marc Martínez** como parte del módulo 8 del *Máster en Behavioral Data Science* – Universidad de Barcelona.  
Profesores tutores: **Dr. David Leiva Ureña**, **Dra. Mireia Ribera Turró**

¿Feedback o sugerencias? ¡Bienvenidas!
