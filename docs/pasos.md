# 🛠️ Protocolo de Limpieza y Resolución de Bloqueos

Este documento detalla las decisiones técnicas tomadas para garantizar la integridad de los datos del proyecto **Buffet Casa Chen**.

## 🧱 Resolución de Bloqueos
Durante el desarrollo, identificamos y solucionamos los siguientes puntos críticos:
1.  **Limpieza de Datos:** Decisión de eliminar registros duplicados específicos para no sesgar la frecuencia de consumo.
2.  **Imputación:** Uso de la media para la Edad y la moda para la Cocina para mantener la representatividad del dataset.
3.  **Atomización:** Desgranar cada tarea en pasos mínimos (Profiling -> Cleaning -> Analysis -> Conclusions) para evitar la saturación del equipo.

## 🧹 Acciones Técnicas Realizadas

### 1. Inspección y Selección
*   **Columnas Eliminadas:** `Area_code`, por carecer de relevancia para el análisis de comportamiento.
*   **Filtrado Inicial:** Identificación de nulos mediante `=CONTAR.BLANCO()` en Excel y auditoría visual de estructura.

### 2. Depuración de Registros (n)
*   **Borrados por Nulos:** Se eliminaron 4 registros con género en blanco (IDs: 200, 128, 125, 162) y 1 con estado civil ausente (ID: 23).
*   **Duplicados:** Se eliminaron **20 filas idénticas** y **9 IDs duplicados** que presentaban un patrón de error en el sistema (ID original + 1000).

### 3. Imputación y Normalización
*   **Edad (Age):** 5 registros en blanco imputados con la media del dataset (**40.13 años**).
*   **Cuisine:** 2 registros imputados con la moda (**Indian**).
*   **Estandarización de Categorías:** 
    *   Fusión de "Sushi" y "Seafood" dentro de la categoría **"Japanese"**.
    *   Unificación de términos redundantes en Género, Tabaco y Alcohol.

### 4. Análisis de Dispersión (Varianza)
Se realizó un análisis profundo de la consistencia de las valoraciones por ubicación:
*   **Baja Dispersión (Consistencia):** Tamaraceite (0.92) y Triana (0.94).
*   **Alta Dispersión (Polarización):** Siete Palmas (1.48). 
*   *Decisión:* Se recomendó al cliente analizar turnos específicos en Siete Palmas para identificar la causa de las opiniones contradictorias.

---

## 🛠️ Herramientas y Aprendizaje Técnico
Para la manipulación eficiente de estos datos, se aplicaron técnicas de **transposición de datos** y atajos de teclado avanzados (`Ctrl+A`, `Shift+Tab`) para agilizar el flujo de trabajo en la fase de Excel Analytics.
