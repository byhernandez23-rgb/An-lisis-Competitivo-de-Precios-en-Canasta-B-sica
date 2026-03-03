# An-lisis-Competitivo-de-Precios-en-Canasta-B-sica
Desarrollar un dashboard analítico en Power BI para monitorear y comparar precios de productos de la canasta básica (PACIC).

El dataset contiene información estructurada con las siguientes variables:

Producto
Presentación
Marca
Categoría
Precio
Fecha_Registro
Cadena_Comercial
Giro
Estado
Municipio

  Fuente: Monitoreo de precios PACIC (simulación para análisis).

Proceso de Transformación (Power Query)

Se realizaron las siguientes transformaciones:

Limpieza del símbolo $ en precio
Conversión a tipo decimal
Conversión de Fecha_Registro a formato Date
Creación de columnas temporales (Año, Mes)

Normalización del modelo para análisis por categoría y cadena
Esto permitió un modelo listo para análisis estadístico y comparativo.

Estructura del Dashboard

El proyecto contiene dos páginas principales:
Página 1 – Executive Overview
Diseñada para toma de decisiones rápidas.

Incluye:
Precio Promedio General
Precio Máximo y Mínimo
Rango de Precio
Coeficiente de Variación
Mapa de Precio Promedio por Estado
Comparación por Categoría vs Benchmark de Mercado

Página 2 – Análisis Detallado

Enfoque analítico profundo:

Desviación Estándar por Categoría
Coeficiente de Variación por Cadena
Comparación dinámica vs promedio de mercado

5. Métricas Clave (DAX)
Precio Promedio
Precio Promedio = AVERAGE(Precios[Precio])

Precio Promedio Mercado (Benchmark)
Precio Promedio Mercado =
CALCULATE(
    [Precio Promedio],
    REMOVEFILTERS(Precios[Cadena_Comercial])
)

Coeficiente de Variación
Coeficiente Variación =
DIVIDE(
    STDEV.P(Precios[Precio]),
    [Precio Promedio]
)

Ranking Dinámico (Top 5)
Ranking Producto =
RANKX(
    ALLSELECTED(Precios[Producto]),
    [Precio Promedio],
    ,
    DESC,
    DENSE
)

6. Principales Insights

Se identificaron diferencias significativas de precio entre cadenas comerciales en categorías clave.
Algunas categorías presentan alta dispersión (CV > 20%), lo que indica estrategias de pricing heterogéneas.
Existen productos consistentemente por encima del benchmark de mercado, lo que puede representar oportunidades de ajuste competitivo.
La variabilidad regional sugiere posible impacto logístico o diferencias en estructura de costos.

7. Valor Analítico del Proyecto

Este proyecto demuestra:

Modelado de datos en Power BI
Dominio de contexto de filtro en DAX
Implementación de métricas estadísticas (Desviación estándar y CV)
Construcción de benchmarks dinámicos
Storytelling ejecutivo basado en datos

Herramientas Utilizadas

Power BI Desktop
DAX
Power Query
Modelado dimensional ligero

Posibles Extensiones

Normalización de precios por unidad (100g / 100ml)
Análisis temporal de inflación
Índice compuesto de riesgo de sobreprecio
Simulación de elasticidad de demanda

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/61d04b29-2ff1-45b4-b18b-9a8cc841cd59" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4d78bf75-a681-4e47-83da-cec93a13e79f" />

Autor

Miguel Ángel Hernández
Data Analyst | Business Intelligence | Pricing & Retail Analytics



