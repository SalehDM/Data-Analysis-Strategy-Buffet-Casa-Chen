# 🍱 Data Analysis & Strategy: Buffet Casa Chen (Las Canteras, Gran Canaria) 📊

![Dashboard Preview](images/dashboard_preview.png)

## 📌 Resumen del Proyecto
Este repositorio contiene un proyecto integral de consultoría estratégica y Business Intelligence enfocado en el rendimiento operativo, satisfacción del cliente y comportamiento de consumo en el **Buffet Casa Chen** (Las Palmas de Gran Canaria). 

El objetivo central fue auditar, procesar y transformar datos transaccionales y de encuestas del establecimiento para corregir problemas operativos, identificar patrones demográficos de consumo y optimizar la toma de decisiones basada en datos reales de negocio.

**El Reto del Cliente:** *"¿Quiénes son nuestros clientes reales, qué cocina prefieren dentro del buffet y qué factores específicos y estadísticos hacen que nos valoren positivamente?"*

> **Insight Maestro:** Identificamos que el modelo de negocio depende críticamente de un público joven y estudiantil (15-24 años) que representa el **61% de la clientela total**, teniendo una preferencia masiva por la **comida japonesa**. Paralelamente, se detectó un nicho altamente rentable en el segmento de **divorciados** con valoraciones sobresalientes (medias de **4.5 a 4.92/5**). No obstante, se descubrió una alarmante tasa de no-retención del **86.7%**, reorientando la estrategia de la empresa hacia la fidelización digital urgente.

---

## ⚙️ Gestión y Metodología (Agile)
El proyecto se gestionó bajo un marco de trabajo colaborativo de alto rendimiento para asegurar entregables incrementales (MVPs) y evitar bloqueos:
*   **Planificación:** Sprints semanales con reuniones diarias (**Dailies**) de sincronización de 30 minutos.
*   **Seguimiento:** Gestión de flujo de trabajo mediante **Project Board (Kanban)** y Roadmap de objetivos en GitHub.
*   **Comunicación:** Centralizada en servidores de **Discord** y repositorio compartido de documentación en la nube.

---

## 🛠️ Tecnologías y Herramientas Utilizadas
*   **Google Sheets**: Procesamiento analítico, funciones lógicas avanzadas, normalización y *Feature Engineering*.
*   **Google Looker Studio**: Modelado de datos, diseño de interfaz interactiva y visualización de KPIs de negocio.
*   **Markdown**: Documentación técnica estructurada.

---

## 📈 Ciclo de Vida del Proyecto & Pipeline de Datos

### 1. Data Profiling & Cleaning (ETL)
Se realizó un proceso riguroso de auditoría analítica sobre la base de datos original para asegurar la máxima fiabilidad en las conclusiones estratégicas:
*   **Depuración de Redundancias:** Eliminación de **20 registros duplicados** a nivel de fila y **9 IDs redundantes** basándose en la llave primaria `User_ID`.
*   **Tratamiento de Inconsistencias y Nulos:** Eliminación de registros huérfanos sin datos demográficos base e imputación de valores vacíos en puntuaciones cuantitativas (`Food_Rating` y `Overall_Rating`) mediante la **mediana estadística** para neutralizar sesgos por valores atípicos (*outliers*).
*   **Estandarización Textual:** Normalización de formatos inconsistentes en variables categóricas (`Gender`, `Marital_Status` y `Activity`).
*   👉 *Para ver las fórmulas y el proceso técnico detallado, consulta el [Log Técnico de Limpieza de Datos](docs/data_cleaning_log.md).*

### 2. Feature Engineering (Enriquecimiento)
*   **Inteligencia Geográfica:** Reemplazo de códigos de área ambiguos por **Códigos Postales oficiales (ES-3500X)** de Las Palmas de Gran Canaria (Vegueta, Triana, Mesa y López, Tamaraceite, Siete Palmas) para habilitar mapas coropléticos interactivos.
*   **Cálculo Dinámico de Edad:** Conversión del año de nacimiento (`YOB`) a edad biológica actual (`Age`) para facilitar las agrupaciones y filtros demográficos por generación (Generación Z y Millennials).
*   **Mapeo de Presupuesto:** Transformación de la escala numérica discreta original (`Budget Num` del 1 al 5) a etiquetas semánticas cualitativas legibles de forma directa (`Very Low` a `Very High`).

---

## 📊 Hallazgos Estratégicos (Deep Dive)

Tras consolidar el pipeline de datos y construir el cuadro de mando interactivo en Looker Studio, se extrajeron las siguientes realidades latentes del negocio:

*   **📍 Análisis por Ubicación:** Tamaraceite lidera la satisfacción general del buffet (Mediana de 3.5), mientras que la zona de Mesa y López presenta el rendimiento más bajo y requiere optimización operativa urgente (Mediana de 3.0). Por su parte, Siete Palmas muestra opiniones altamente polarizadas registrando una **Varianza de 1.48**.
*   **👥 Psicografía y Consumo:** Los clientes casados tienden a puntuar consistentemente a la baja (promedios entre 2.37 y 2.89), mientras que el consumo social de alcohol se correlaciona directamente con las mejores experiencias de usuario y notas más altas de satisfacción.
*   **🔴 Riesgo Operativo (La Paradoja Filipina):** La cocina Filipina es una de las más consumidas en volumen, pero registra la satisfacción más baja con un **3.04/5.00** (-0.16 por debajo de la media global). Esto sugiere una necesidad urgente de revisar recetas, sazón o frescura de insumos en barra.
*   **🟢 Éxito de la Cocina Japonesa:** Se consolida como la diferenciación clave y el producto estrella del buffet, liderando los índices de satisfacción con una media de **3.58/5.00** (+0.38 por encima de la media global de 3.2), especialmente impulsada por el segmento de 15 a 24 años.

---

## 🚀 Recomendaciones de Negocio

Basado en la evidencia sólida de los datos, se propusieron tres líneas de acción estratégicas para la gerencia de Casa Chen:
1.  **Fidelización Digital Segmentada:** Implementar campañas de marketing geolocalizadas en TikTok e Instagram para el target joven (15-24 años), utilizando la comida japonesa como gancho principal para revertir el **86.7%** de clientes no-leales mediante cupones o programas de puntos por QR.
2.  **Estandarización del Servicio Operativo:** Realizar una auditoría cruzada interna para replicar las buenas prácticas de servicio y cocina de Tamaraceite en la ubicación de Siete Palmas, mitigando su alta varianza de opiniones y estabilizando la marca.
3.  **Optimización del Espacio de Barra:** Reducir la variedad e inventario de la cocina Italiana (la menos consumida en todos los segmentos) y reasignar esos recursos económicos y metros de barra a potenciar la estación de Sushi y cocina Japonesa.

---

## 📁 Estructura del Repositorio

```text
/
├── data/
│   ├── BBDD_Original.xlsx             # Datos crudos con inconsistencias y nulos
│   └── BBDD_Processed_Final.xlsx      # Base de datos optimizada y normalizada
├── docs/
│   ├── data_cleaning_log.md           # Registro técnico detallado de limpieza y fórmulas
│   └── analisis_cualitativo.md        # Reporte extendido en Markdown con los insights de negocio
├── images/
│   └── dashboard_preview.png          # Captura de pantalla del cuadro de mando
└── README.md                          # Presentación principal del proyecto
```

---

## 🔗 Documentación y Enlaces
*   📊 [**Dashboard Interactivo en Looker Studio**](https://goo.su)
*   🧹 [**Log Técnico de Limpieza de Datos (Markdown)**](docs/data_cleaning_log.md)
*   📑 [**Informe de Análisis Cualitativo Completo (Markdown)**](docs/analisis_cualitativo.md)

---

## 👥 Equipo y Colaboración
Este proyecto fue desarrollado de manera colaborativa, participando todos los integrantes de forma equitativa en el ciclo completo de ingeniería de datos, modelado analítico y consultoría estratégica:

*   **Saleh Daf** — [GitHub Profile](https://github.com)
*   **Alberto Domínguez** — [GitHub Profile](https://github.com)
*   **Azahara García** — [GitHub Profile](https://github.com)

---
*Nota: Este proyecto fue realizado en el marco de un Bootcamp de Data Analytics, simulando una entrega profesional con rigor metodológico para un cliente real.*
