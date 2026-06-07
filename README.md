# Prediccion-perdida-clientes-de-Model-Fitness-

🏋️ Predicción de Abandono y Segmentación de Clientes — Gimnasio

Machine Learning aplicado a la retención de clientes en fitness.
De los datos crudos a estrategias de fidelización: análisis de correlación, clustering jerárquico, K-Means y segmentación accionable para reducir churn y maximizar el valor de vida del cliente.

🚀 Sobre Este Proyecto 
"No solo segmenté clientes. Diseñé un sistema de alerta temprana de abandono con acciones concretas para cada perfil."

| Competencia                   | Evidencia en el proyecto                                                                                              |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **🧠 Pensamiento crítico**    | Identifiqué que género y teléfono son ruido, no predictores — evitando estrategias basadas en sesgos                  |
| **📊 Storytelling con datos** | Cada insight técnico se tradujo en una acción de negocio con costo e impacto estimado                                 |
| **🤖 ML aplicado a negocio**  | K-Means no fue un ejercicio académico: definió 2 perfiles claros con estrategias diferenciadas                        |
| **⚖️ Trade-off analysis**     | Elegí k=2 sobre k=5 porque la separación accionable importa más que la granularidad técnica                           |
| **💰 Orientación a ROI**      | Las recomendaciones distinguen entre incentivos de "bajo costo" para riesgo alto y "inversión" para clientes valiosos |


¿Por qué este proyecto?


En la industria del fitness, adquirir un nuevo cliente cuesta 5× más que retener uno existente. Este proyecto demuestra cómo transformar datos de membresía en estrategias de retención personalizadas, combinando análisis estadístico con aprendizaje no supervisado para identificar quién se va a ir... antes de que lo haga.

Competencias demostradas:
🔬 Análisis exploratorio con enfoque en variables predictoras de churn

🤖 Clustering jerárquico y K-Means para segmentación de clientes

📊 PCA para visualización de alta dimensionalidad

💼 Traducción de insights técnicos en acciones de negocio concretas

📊 1. Análisis de Factores de Abandono (Churn Analysis)
Variables Categóricas — Impacto en Retención

| Factor                                          |    Impacto en Abandono   | Insight de Negocio                                     |
| ----------------------------------------------- | :----------------------: | ------------------------------------------------------ |
| **🚶 Near\_Location** (vive cerca)              | **↓ 20%** menos abandono | 🔥 El factor más importante. Proximidad = compromiso   |
| **🤝 Promo\_friends** (inscripción por amigo)   | **↓ 16%** menos abandono | Socialización reduce churn. El "efecto tribu" funciona |
| **👥 Group\_visits** (asiste a clases grupales) | **↓ 16%** menos abandono | Comunidad = retención. Mismo patrón que promo\_friends |
| **🏢 Partner** (empresa asociada)               | **↓ 14%** menos abandono | Beneficios corporativos generan lealtad                |
| **⚧ Gender**                                    |      Sin diferencia      | No es predictor relevante                              |
| **📱 Phone**                                    |      Sin diferencia      | No aporta información predictiva                       |



.
📈 2. Matriz de Correlación — Variables Numéricas


🔥 Correlaciones más fuertes con Churn (abandono)

| Variable                                  | Correlación con Churn | Interpretación                                          |
| ----------------------------------------- | :-------------------: | ------------------------------------------------------- |
| **Lifetime**                              |       **-0.44**       | ⭐ Más tiempo en el gimnasio = menor abandono            |
| **Avg\_class\_frequency\_current\_month** |       **-0.41**       | Frecuencia reciente de visitas protege contra churn     |
| **Contract\_period**                      |       **-0.39**       | Contratos más largos = mayor compromiso                 |
| **Month\_to\_end\_contract**              |       **-0.38**       | Cuando el contrato se acerca a terminar, el riesgo sube |
| **Age**                                   |       **-0.40**       | Clientes mayores son más leales                         |


🤖 3. Clustering — Segmentación de Clientes

🔗 Clustering Jerárquico (Dendrograma)

El análisis del dendrograma sugiere k = 3 clusters como punto de corte óptimo (línea roja antes del salto grande entre niveles).

📐 K-Means — Selección del número óptimo de clusters

| Método                    | Clusters Óptimos | Observación                     |
| ------------------------- | :--------------: | ------------------------------- |
| **Método del Codo**       |         5        | Inercia se estabiliza en k=5    |
| **Score de Silhouette**   |       **2**      | Mayor separación entre clusters |
| **Clustering Jerárquico** |         3        | Consistencia estructural        |


👤 4. Perfiles de Clusters (K-Means, k=2)

| Característica     | Cluster 0 (2,537 usuarios) | Cluster 1 (1,463 usuarios) | Diferencia |
| ------------------ | :------------------------: | :------------------------: | :--------: |
| **Near\_Location** |            0.79            |          **0.94**          |   +15 pts  |
| **Partner**        |            0.34            |          **0.74**          |   +40 pts  |
| **Promo\_friends** |            0.18            |          **0.53**          |   +35 pts  |
| **Phone**          |            0.91            |            0.90            |     ~0     |
| **Gender**         |            0.51            |            0.52            |     ~0     |


🏷️ Perfiles identificados

| Cluster | Perfil                                                                   | Tasa de Cancelación | Estrategia                                               |
| :-----: | ------------------------------------------------------------------------ | :-----------------: | -------------------------------------------------------- |
|  **0**  | "Cliente Casual" — vive lejos, poco social, sin beneficios corporativos  |     🔴 **MAYOR**    | Incentivos de bajo costo, clases grupales introductorias |
|  **1**  | "Cliente Comprometido" — vive cerca, social, con beneficios corporativos |     🟢 **MENOR**    | Programa de fidelización, referidos, membresía premium   |


5. Estrategias de Retención por Segmento

Para el Cluster de Alto Riesgo (Cluster 0 / Grupos 3, 4 en k=5)

| Problema                   | Acción                                    |  Costo  |        Impacto esperado       |
| -------------------------- | ----------------------------------------- | :-----: | :---------------------------: |
| Baja frecuencia de visitas | Clases grupales con descuento             | 💰 Bajo |   Aumentar engagement social  |
| Contrato próximo a vencer  | Recordatorios + ofertas de renovación     | 💰 Bajo | Reducir churn por vencimiento |
| Gasto adicional bajo       | Promociones en cafetería/spa del gimnasio | 💰 Bajo |        Incrementar LTV        |


Para el Cluster de Bajo Riesgo (Cluster 1 / Grupos 1, 2 en k=5)

| Oportunidad              | Acción                                      |   Costo  |          Impacto esperado          |
| ------------------------ | ------------------------------------------- | :------: | :--------------------------------: |
| Alta lealtad             | Programa de embajadores (referidos)         | 💰 Medio | CAC reducido, crecimiento orgánico |
| Alto gasto adicional     | Membresía premium con beneficios exclusivos | 💰 Medio |            Aumentar ARPU           |
| Socialización confirmada | Eventos comunitarios, competencias grupales | 💰 Medio |       Reforzar "efecto tribu"      |

🏠 Factor Proximidad (Near_Location)
El factor más predictor de retención. Clientes que viven cerca tienen 20% menos abandono.
Acción: Campañas geo-targeting para captar usuarios en un radio de 2km
Acción: Alianzas con transporte público / estacionamiento para reducir fricción de distancia


Resultado medible propuesto


Implementar las estrategias sugeridas podría reducir el churn del Cluster 0 (alto riesgo) en un 15-20% mediante:

Clases grupales con descuento (↓ 16% churn confirmado por datos)

Campañas de referidos para captar clientes similares al Cluster 1 (↓ 16% churn)

Geo-targeting para aumentar la proporción de "Near_Location" (↓ 20% churn)


