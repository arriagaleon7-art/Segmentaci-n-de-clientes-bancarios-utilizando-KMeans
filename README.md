# Segmentación de clientes bancarios utilizando KMeans
Segmentación de clientes bancarios utilizando el algoritmo de Machine Learning No Supervisado, KMeans.

## Resumen del proyecto

 A través de un  proceso de EDA, ingeniería de variables y análisis demográfico, en una base de 10,000+ clientes se identificaron 5 perfiles de comportamiento clave. Se proponen estrategías en cada segmento para optimizar la toma de decisiones  y la gestión del riesgo crediticio.

## Entendimiento del negocio
En el sector bancario actual, tratar a todos los clientes por igual resulta ineficiente y costoso. La segmentación permite diseñar ofertas de alto valor que se apeguen al perfil de grupos de clientes aumentando el nivel de confianza en la institución y con ello la fidelidad. Además, al identificar grupos de alto riesgo con alta tasa de utilización de crédito y bajos ingresos, el banco puede actuar proactivamente para prevenir el impago. 

## Comprensión de los datos
Los datos provienen de una organización bancaria ficticia. El conteido es el siguiente:

Como un primer paso hemos analizado brevemente el contenido del data set. El cual consta de 10127 observaciones no nulas no repetidas y 14 columnas.

### Diccionario de Datos

| Variable | Tipo de Dato | Descripción |
| :--- | :--- | :--- |
| **customer_id** | `int64` | Identificador único del cliente. |
| **age** | `int64` | Edad del cliente en años. |
| **gender** | `object` | Género del cliente (M = Masculino, F = Femenino). |
| **dependent_count** | `int64` | Número de personas que dependen económicamente del cliente. |
| **education_level** | `object` | Nivel educativo máximo alcanzado. |
| **marital_status** | `object` | Estado civil del cliente. |
| **estimated_income** | `int64` | Ingreso anual estimado del cliente. |
| **months_on_book** | `int64` | Antigüedad del cliente en el banco (meses). |
| **total_relationship_count** | `int64` | Número de productos contratados por el cliente. |
| **months_inactive_12_mon** | `int64` | Meses de inactividad en el último año. |
| **credit_limit** | `float64` | Límite de crédito máximo en la tarjeta. |
| **total_trans_amount** | `int64` | Monto total transaccionado en los últimos 12 meses. |
| **total_trans_count** | `int64` | Cantidad total de transacciones en los últimos 12 meses. |
| **avg_utilization_ratio** | `float64` | Índice de utilización de la línea de crédito (0 a 1). |
| **avg_transaction_value** | `float64` | *Feature Engineering*: Monto promedio por transacción individual. |

## Modelización y evaluación
El análisis exploratorio de datos EDA permitió encontrar patrones en lo datos, identificar datos atípicos e indagar entre correlacion entre variables. El análisis del método del codo, complementado con el coeficiente de silueta, permitió identificar 5 segmentos con los que se entrenó el modelo.

Conclusión
El análisis de perfil de los cluster arrojó lo siguiente:

*   **Cluster 0:** Segmento con más miembros. Caracterizado por ingresos bajos y líneas de crédito bajo en comparación. La edad promedio es más alta en este cluster y presenta la tasa de utilización  más alta con el promedio de productos contratados más alto.
**Perfil demográfico:** Está constituido mayormente por mujeres casadas (86.55%) y divorciados (13.45%).
*   **Cluster 1:** Posee uno de los ingresos más altos y el límite de crédito más alto. Tienen la tasa de utilización más baja, su nivel de transacción es sólido. **Perfil demográfico:** Se constituye mayormente por hombres solteros (99.94%).
* **Cluster 2:** Es el grupo con la menor edad promedio y el mayor número de dependientes. Es el cluster más pequeño. **Perfil demográfico:** El estado civil de este segmento es desconocido se constituye en igual cantidad por hombres y mujeres.
* **cluster 3:** Ingresos bajos y límites de crédito reducidos. A diferencia del cluster 0 este segmento tiene una inactividad ligeramente mayor y es el segundo segmento más numeroso. También tiene una utilización alta del crédito. **Perfil demográfico:** Compuesto mayoritariamente por mujeres solteras(99.87%) y divorciadas (0.013%)
* **Cluster 4:** Segmento con el ingreso promedio más alto (\$92,827) y un límite de crédito generoso (\$13,460). Tienen una tasa de utilización baja y son los que menos trasacciones realizan. **Perfil demográfico:** Se compone mayoritariamente por hombres casados (86%) y divorciados (14%)
