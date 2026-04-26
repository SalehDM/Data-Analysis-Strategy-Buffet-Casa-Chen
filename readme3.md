# 🍱 Data Analysis & Strategy: Buffet Casa Chen (Gran Canaria)

![Dashboard Preview](images/dashboard_preview.png)

## 📌 Resumen del Proyecto
Consultoría de datos para el restaurante **Buffet Casa Chen**, ubicado en la zona de Las Canteras. El proyecto transforma una base de datos bruta en una estrategia de negocio para optimizar la fidelización y mejorar la experiencia del cliente.

**Solicitud del Cliente:** "¿Quiénes son nuestros clientes, qué cocina prefieren y qué factores influyen en su valoración?"

> **Insight Maestro:** Identificamos un nicho estratégico de **público joven (16–25 años)** y un segmento de **divorciados** con valoraciones altísimas (hasta 4.92/5), ambos con una preferencia crítica por la **Comida Japonesa**.

---

## ⚙️ Gestión y Metodología (Agile)
El proyecto se gestionó bajo un marco de trabajo colaborativo para evitar bloqueos y asegurar MVPs:
*   **Gestión:** Sprints diarios (**Dailies**) de 30 min y seguimiento mediante **Project Board (Kanban)** y Roadmap.
*   **Comunicación:** Centralizada en **Discord** y repositorio compartido en **Google Drive**.
*   **Stack Técnico:** Python (Pandas/NumPy), Google Looker Studio y Excel avanzado.

---

## 📈 Ciclo de Vida del Proyecto

### 1. Data Profiling & Cleaning (ETL)
*   **Auditoría:** Análisis descriptivo preliminar (media, mediana, desviación típica) de variables como Edad, Género y Budget.
*   **Depuración:** Eliminación de **20 filas duplicadas** y **9 IDs redundantes**.
*   **Tratamiento de Nulos:** Eliminación de registros críticos sin género (IDs 200, 128, 125, 162) e imputación de edad mediante la **media (n=5)** y cocina mediante la **moda (n=2)**.
*   👉 [Ver detalle técnico de Limpieza y Bloqueos](docs/Pasos_Data_Cleaning.md)

### 2. Hallazgos Estratégicos (Deep Dive)
*   **📍 Análisis por Ubicación:** Tamaraceite lidera en satisfacción (Mediana 3.5), mientras que Mesa y López presenta oportunidades de mejora (Mediana 3.0). Siete Palmas muestra opiniones polarizadas (**Varianza 1.48**).
*   **👥 Psicografía:** Los clientes casados tienden a puntuar más bajo (2.37-2.89), mientras que el consumo social de alcohol se correlaciona con las mejores experiencias.
*   **🍱 Cocina:** La cocina japonesa es la diferenciación clave del buffet.

---

## 🚀 Recomendaciones de Negocio
1.  **Fidelización Digital:** Campañas segmentadas en TikTok e Instagram para el target joven (16-25 años).
2.  **Optimización de Menú:** Ampliación de la oferta japonesa, el driver de valor mejor puntuado.
3.  **Estandarización de Servicio:** Replicar las buenas prácticas de Tamaraceite en las ubicaciones con mayor varianza (Siete Palmas).

---

## 🔗 Enlaces y Documentación
*   📊 [**Dashboard Interactivo (Looker Studio)**](TU_LINK_AQUI)
*   📑 [**Informe de Gráficas Pre/Post**](reports/Comparativa_Pre_Post.pdf)
*   📽️ [**Presentación Ejecutiva**](reports/Presentacion_Final.pdf)

---

## 👥 Equipo
*   **Tu Nombre** — [GitHub]
*   **Integrante 2** — [GitHub]
*   **Integrante 3** — [GitHub]
