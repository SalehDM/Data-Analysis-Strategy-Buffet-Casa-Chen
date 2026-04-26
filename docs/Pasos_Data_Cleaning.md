# 🛠️ Protocolo de Limpieza y Transformación de Datos (ETL)

Este documento detalla el proceso técnico seguido para transformar la base de datos bruta del **Buffet Casa Chen** en un dataset optimizado para el análisis estratégico y la visualización en Looker Studio.

## 🔍 1. Inspección y Auditoría de Datos
Antes de cualquier intervención, se realizó un perfilado de los datos (Data Profiling) para entender la estructura de `BBDD_Original.xlsx`:
*   **Identificación de errores:** Se detectaron inconsistencias en el registro de tipos de cocina y duplicidad en los IDs de clientes.
*   **Valores Atípicos (Outliers):** Se analizaron presupuestos inusualmente altos que podrían sesgar el análisis de "Budget" por rango de edad.

## 🗑️ 2. Eliminación de Datos Irrelevantes o Duplicados
*   **Depuración:** Se eliminaron 20 registros duplicados y 9 IDs redundantes para evitar la sobreestimación de la frecuencia de visita.
*   **Simplificación:** Se removieron columnas administrativas que no aportaban valor al objetivo de negocio (fidelización y satisfacción).

## ❌ 3. Gestión de Valores Faltantes (Data Imputation)
Para no perder volumen de muestra en el segmento joven (16-25 años):
*   **Imputación Estadística:** Los valores faltantes en campos críticos como "Edad" y "Presupuesto" se trataron mediante la **mediana** para evitar el sesgo de los valores extremos.
*   **Filtrado:** Se eliminaron filas con más de un 50% de campos nulos para garantizar la fiabilidad del análisis de correlación.

## 🔢 4. Normalización y Estandarización
Este fue el paso más crítico para el análisis de la cocina japonesa:
*   **Categorización:** Se unificaron etiquetas de texto (Ej: "Japonesa", "Sushi", "Japo" → **Japonesa**).
*   **Formateo:** Estandarización de formatos numéricos y de moneda para el cálculo de KPIs financieros.

## 📊 5. Transformación de Variables (Feature Engineering)
*   **Segmentación Etaria:** Creación de la columna "Rango de Edad" para facilitar la visualización del público objetivo identificado (16-25 años).
*   **Rating Score:** Normalización de las valoraciones de Comida, Servicio y Ambiente en una escala homogénea para el cálculo del Rating Global.

## 🧪 6. Validación y Exportación
*   **Pruebas de Consistencia:** Se verificó que la suma de los segmentos coincidiera con el total de la base de datos tras la limpieza.
*   **Guardado Final:** Exportación del archivo `data/BBDD_Processed_Final.xlsx` listo para su conexión con el dashboard.

---
> **Impacto del proceso:** Gracias a la eliminación de duplicados y la estandarización de categorías, se eliminó el sesgo en las preferencias gastronómicas, asegurando que la recomendación de potenciar el menú japonés se base en datos íntegros y representativos del comportamiento real del cliente.
