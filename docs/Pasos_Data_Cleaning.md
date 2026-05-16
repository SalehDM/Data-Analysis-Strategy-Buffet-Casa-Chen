# 🛠️ Protocolo de Limpieza y Transformación de Datos (ETL)

Este documento detalla el proceso técnico seguido para transformar la base de datos bruta del **Buffet Casa Chen** en un dataset optimizado para el análisis estratégico y la visualización en Looker Studio.

## 🔍 1. Inspección y Auditoría de Datos
Antes de cualquier intervención, se realizó un perfilado de los datos (*Data Profiling*) para entender la estructura de `BBDD_Original.xlsx`:
* **Identificación de errores:** Se detectaron inconsistencias de formato en los tipos de cocina y duplicidad en los registros de clientes.
* **Filtrado Inicial:** Identificación de valores nulos mediante la función `=CONTAR.BLANCO()` en Excel y auditoría visual de la estructura general.

## 🗑️ 2. Eliminación de Datos Irrelevantes o Duplicados
* **Depuración:** Se eliminaron **20 filas idénticas** y **9 IDs duplicados** que presentaban un patrón de error en el sistema de tickets (ID original + 1000), evitando la sobreestimación de la frecuencia de visita.
* **Simplificación:** Se removió la columna administrativa `Area_code` por carecer de relevancia para el análisis de comportamiento y segmentación de clientes en sala.

## ❌ 3. Gestión de Valores Faltantes (Data Imputation)
Para no perder volumen de muestra y mantener la integridad del dataset:
* **Borrados por Nulos:** Se eliminaron 4 registros con el campo de género en blanco (IDs: 200, 128, 125, 162) y 1 con estado civil ausente (ID: 23).
* **Imputación Estadística:** 2 registros faltantes en la columna "Cuisine" se trataron mediante la **moda** del dataset, asignando la categoría predominante (**Japanese**) para evitar sesgos en el análisis de consumo.

## 🔢 4. Normalización y Estandarización
Este fue el paso más crítico para garantizar la coherencia visual en las gráficas de Looker Studio:
* **Categorización:** Se unificaron términos redundantes y errores tipográficos en variables de perfil de usuario (Género, Tabaco y Alcohol).
* **Segmentación Limpia:** Se mantuvieron **"Japanese"** y **"Seafood"** como dimensiones independientes para evaluar con precisión el impacto del sushi frente al resto de productos marinos.

## 📊 5. Transformación de Variables (Feature Engineering)
* **Segmentación Etaria:** Creación de la columna "Rango de Edad" estructurada en intervalos específicos (**15-24**, 25-34, 35-44, etc.) para facilitar la visualización del público objetivo.
* **Rating Scores:** Consolidación homogénea de las métricas de *Food Rating* y *Service Rating* para permitir el desglose directo de la satisfacción por tipo de gastronomía.

## 🧪 6. Validación y Exportación
* **Pruebas de Consistencia:** Se verificó que la suma de los segmentos de actividad coincidiera con el total del dataset limpio (61% Estudiantes y 39% Profesionales).
* **Análisis del Rating:** Se validó en el backend de datos la consolidación del score general (*Overall Rating*) de **3,2** sobre 5.
* **Guardado Final:** Exportación del archivo final listo para su conexión directa con el dashboard de Looker Studio.

---
> 💡 **Impacto del proceso:** Gracias a la eliminación de duplicados y la estandarización de categorías, se eliminó el sesgo en las preferencias gastronómicas. Esto aseguró que la recomendación estratégica de potenciar el menú japonés se base en datos íntegros, demostrando estadísticamente que este segmento lidera en consumo en el público joven y alcanza el rating más alto con un **3,58** (+0,36 sobre la media).
