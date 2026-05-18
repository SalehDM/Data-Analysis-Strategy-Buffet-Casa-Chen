# 🍜 Business Intelligence & Data Analytics: Buffet Casa Chen 📊

Este repositorio contiene un proyecto de análisis de datos y Business Intelligence enfocado en el rendimiento operativo, satisfacción del cliente y comportamiento de consumo en el **Buffet Casa Chen** (Las Palmas de Gran Canaria). 

El objetivo principal es transformar datos transaccionales y de encuestas en insights estratégicos para mejorar la retención de clientes y optimizar la oferta gastronómica.

---

## 🗺️ Estructura del Repositorio

```text
/
├── data/
│   ├── BBDD_Original.xlsx             # Datos crudos con inconsistencias y nulos
│   └── BBDD_Processed_Final.xlsx      # Base de datos optimizada y normalizada
├── docs/
│   ├── data_cleaning_log.md           # Registro técnico del pipeline de limpieza
│   └── Analisis_Cualitativo.pdf       # Reporte detallado de hallazgos de negocio
├── images/
│   └── dashboard_preview.png          # Captura de pantalla del cuadro de mando
└── README.md                          # Presentación principal del proyecto
```

---

## 🛠️ Tecnologías y Herramientas Utilizadas
*   **Google Sheets**: Procesamiento, normalización, Feature Engineering e imputación de datos.
*   **Looker Studio**: Construcción del dashboard interactivo y visualización de KPIs de negocio.
*   **Markdown**: Documentación técnica del proyecto.

---

## 📈 Hallazgos Clave del Dashboard (Insights de Negocio)

Tras consolidar los datos y construir el cuadro de mando interactivo, se identificaron los siguientes puntos críticos:

### 👥 Perfil del Consumidor
*   **Segmentación Demográfica**: El buffet es altamente dependiente del sector académico; los **estudiantes representan el 61%** de la clientela, concentrándose mayoritariamente en el rango de **15 a 24 años**.
*   **Alerta de Retención (Fidelización)**: Existe un problema crítico en la recurrencia del cliente. El **86.7% de los usuarios son catalogados como "No Leales" (FALSE)**, frente a un escaso 13.3% de clientes recurrentes.

### 🍱 Preferencias Gastronómicas y Calidad
*   **Platos Estrella**: Las cocinas **Filipina y Japonesa** lideran el volumen de consumo general. La cocina Japonesa es un éxito exclusivo y masivo en el segmento joven (15-24 años).
*   **Discrepancia Calidad vs. Volumen (Cocina Filipina)**: A pesar de ser una de las cocinas más ordenadas, la cocina Filipina registra la satisfacción más baja con un **3.04/5.00** (-0.17 por debajo de la media). Esto sugiere una necesidad urgente de revisar recetas o frescura de insumos.
*   **Líder en Satisfacción**: La cocina **Japonesa** no solo tiene un alto volumen, sino que es la mejor valorada con una puntuación media de **3.58/5.00** (+0.36 por encima de la media global de 3.2).

---

## 🧹 Pipeline de Limpieza y Enriquecimiento (Resumen)
Para asegurar la fiabilidad de las métricas en Looker Studio, los datos originales sufrieron un proceso riguroso de *Data Wrangling*:
1.  **Remoción de duplicados**: Eliminación de registros redundantes por `User_ID`.
2.  **Inteligencia Geográfica**: Reemplazo de códigos de área ambiguos por **Códigos Postales oficiales (ES-3500X)** mapeados a los barrios de Las Palmas de Gran Canaria (Vegueta, Triana, Mesa y López, etc.).
3.  **Feature Engineering**: Conversión de años de nacimiento (`YOB`) a edades biológicas actuales y transformación de la escala de presupuesto a variables cualitativas (`Very Low` a `Very High`).

*Para ver las fórmulas y el proceso técnico detallado, consulta el [Log de Limpieza de Datos](docs/data_cleaning_log.md).*

---
