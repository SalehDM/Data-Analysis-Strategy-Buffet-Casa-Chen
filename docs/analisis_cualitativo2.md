# 📈 Análisis Cualitativo e Insights de Negocio: Buffet Casa Chen

Este informe ejecutivo sintetiza los hallazgos críticos derivados de las tres páginas del cuadro de mando interactivo en Looker Studio. El objetivo es diagnosticar la situación comercial del buffet y proponer planes de acción basados en datos.

---

## 🎯 1. Perfil y Comportamiento del Consumidor (Customer Profile)

### Diagnóstico Demográfico
*   **Dependencia Estudiantil**: El modelo de negocio está fuertemente sostenido por el sector educativo. Los **estudiantes representan el 61%** de la cuota total de mercado, concentrándose mayoritariamente en el rango juvenil de **15 a 24 años**. El 39% restante pertenece a profesionales activos.
*   **Distribución por Estado Civil**: La mitad de la base de clientes está compuesta por solteros (50.3%), seguidos de cerca por clientes casados (43.1%), dejando un nicho minoritario para divorciados (6.6%).

### ⚠️ Alerta Crítica: El Problema de la Retención
*   El hallazgo más alarmante del análisis radica en la fidelidad del cliente: **el 86.7% de los usuarios son catalogados como "No Leales" (FALSE)**. 
*   Solo un **13.3%** regresa habitualmente al buffet. Esto indica que el restaurante funciona como un negocio de atracción única (ensayo) pero falla drásticamente en la experiencia posterior, provocando una alta tasa de abandono (*churn rate*).

---

## 🍜 2. Preferencias de Consumo y Tráfico (Cuisines Consumed)

### Análisis de Popularidad por Volumen
*   Las gastronomías **Filipina y Japonesa** lideran de forma absoluta el volumen de órdenes del buffet.
*   **Fenómeno Generacional**: La cocina Japonesa experimenta un consumo masivo y casi exclusivo por parte del segmento joven de **15 a 24 años**. No tiene tracción en los segmentos de mediana o avanzada edad.
*   **Baja Popularidad**: La cocina **Italiana** se consolida como la menos consumida en todos los segmentos del buffet.

---

## ⭐ 3. Análisis de Satisfacción y Calidad (Ratings)

El buffet registra una puntuación media global de **3.2 / 5.0**. Al cruzar el volumen de consumo con las calificaciones reales, descubrimos una discrepancia operativa severa:


| Tipo de Cocina | Volumen de Consumo | Calificación Promedio | Desviación vs. Media Global (3.2) | Estado de Alerta |
| :--- | :--- | :--- | :--- | :--- |
| **Japonesa** | Muy Alto | **3.58** | `+0.38` 🟢 | **Éxito Absoluto**: El producto estrella en volumen y satisfacción. |
| **Filipina** | Muy Alto | **3.04** | `-0.16` 🔴 | **Riesgo Operativo**: Mucho consumo pero mala calidad percibida. |

### Conclusiones de Satisfacción
1.  **La paradoja Filipina**: Es de los platos más servidos pero peor calificados. Esto destruye la repetición del cliente. El problema puede deberse a la frescura en las bandejas del buffet, sazón o tiempos de exposición.
2.  **El nicho Divorciado**: Aunque representan solo el 6.6% del público, los clientes divorciados califican al establecimiento con un altísimo **4.5 / 5.0** (`+1.29` por encima de la media).

---

## 💡 Recomendaciones Estratégicas para la Gerencia

1.  **Auditoría de Cocina Filipina**: Es urgente revisar las recetas, la temperatura de mantenimiento y la rotación del buffet filipino. Corregir este producto frenará inmediatamente las malas calificaciones.
2.  **Campaña de Fidelización Estudiantil**: Dado que el 61% son estudiantes de 15-24 años apasionados por la comida japonesa, se debe lanzar un programa de lealtad digital (ej. "A la 5ª visita, buffet gratis") enfocado en este plato para subir el indicador de retención actual del 13.3%.
3.  **Optimización del Espacio de Buffet**: Reducir el inventario y variedad de comida Italiana (baja demanda) y reasignar esos costos y metros de barra a potenciar la barra de comida Japonesa (alta demanda y alta satisfacción).
