# 🧹 Log de Limpieza y Transformación de Datos (Data Cleaning)

Este documento detalla el pipeline técnico y las operaciones lógicas ejecutadas en **Google Sheets** para transformar la base de datos cruda (`BBDD_Original.xlsx`) en el conjunto de datos optimizado, limpio y consistente (`BBDD_Processed_Final.xlsx`) para su posterior explotación en Looker Studio.

---

## 🛠️ Fase 1: Limpieza y Normalización

### 1. Eliminación de Registros Duplicados
*   **Problema**: Se detectaron múltiples filas idénticas repetidas para un mismo identificador único de usuario (ej. `User_ID` 4, 26, 41, 42, 47, 52, 59, 83, 84).
*   **Solución**: Se aplicó la función nativa de eliminación de duplicados tomando como llave primaria la columna `User_ID` para asegurar la integridad referencial.

### 2. Estandarización de Variables Categóricas (Texto)
*   **Género (`Gender`)**: Inconsistencias críticas con términos mixtos en inglés, español y formatos (`Male`, `male`, `boy`, `Female`, `female`, `girl`). Se unificó a un estándar binario mediante lógica condicional:
    ```excel
    =SI(O(D2="Male"; D2="male"; D2="boy"); "Male"; "Female")
    ```
*   **Estado Civil (`Marital_Status`)**: Se eliminaron las discrepancias de capitalización (`single`, `Married`, `married`, `divorced`) aplicando una limpieza con la función `NOMPROPIO` para homogeneizar a `Single`, `Married` y `Divorced`.
*   **Ocupación (`Activity`)**: Agrupación taxonómica para consolidar variantes de estudiantes (`Student`, `student`, `Studying`) y trabajadores (`Professional`, `professional`, `Working`).

### 3. Tratamiento e Imputación de Valores Nulos (Missing Values)
*   **Puntuaciones de Calidad (`Ratings`)**: Las celdas vacías en las métricas cuantitativas `Food_Rating` y `Overall_Rating` rompían las tarjetas de promedios. Se imputaron los registros vacíos utilizando la **mediana estadística** del resto de la columna para evitar sesgos por valores atípicos (outliers).
*   **Ubicaciones Geográficas**: Los registros huérfanos con celdas vacías en la zona o barrios se validaron y rellenaron cruzando la consistencia del set de datos.

---

## 🚀 Fase 2: Enriquecimiento de Datos (Feature Engineering)

### 4. Inyección de Inteligencia Geográfica (`CP`)
*   **Acción**: Se eliminó la columna ambigua `Area_code` y se transformó la columna `Location` mapeando los nombres de los barrios reales a sus **Códigos Postales oficiales de Las Palmas de Gran Canaria**, habilitando el uso de mapas coropléticos en Looker Studio:
    *   `Vegueta` \(\rightarrow\) **`ES-35001`**
    *   `Triana` \(\rightarrow\) **`ES-35002`**
    *   `Mesa y López` \(\rightarrow\) **`ES-35010`**
    *   `Tamaraceite` \(\rightarrow\) **`ES-35018`**
    *   `Siete Palmas` \(\rightarrow\) **`ES-35019`**

### 5. Cálculo Dinámico de Edad (`Age`)
*   **Acción**: La columna original del año de nacimiento (`YOB`) dificultaba la segmentación demográfica en tiempo real. Se creó la columna calculada `Age` determinando la edad biológica exacta basada en la fecha de la auditoría del proyecto:
    ```excel
    =SI(ESNUMERO(E2); 2025 - E2; "")
    ```

### 6. Cuantificación y Mapeo de Presupuesto (`Budget`)
*   **Acción**: Se transformó la escala numérica discreta original (`Budget Num` del 1 al 5) en etiquetas categóricas semánticas claras (`Budget`) mediante funciones `SI` anidadas o tablas de búsqueda (`BUSCARV`) para mejorar la legibilidad del dashboard:
    *   `1` $\rightarrow$ **`Very Low`**
    *   `2` $\rightarrow$ **`Low`**
    *   `3` $\rightarrow$ **`Medium`**
    *   `4` $\rightarrow$ **`High`**
    *   `5` $\rightarrow$ **`Very High`**

### 7. Normalización Lógica de Fidelización (`Often_A_S`)
*   **Acción**: La columna que define la recurrencia del cliente contenía formatos lógicos y cadenas de texto cruzadas (`No`, `FALSE`, `Yes`, `TRUE`). Se estandarizó por completo a variables booleanas puras de tipo **`TRUE` / `FALSE`** requeridas por los motores de agregación de Business Intelligence.
