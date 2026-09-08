# Proyecto Final: Estrategia de Inversión Editorial basada en Data Analysis
Proyecto final para el Curso de Data Analysis con Python brindado por Comunidad IT.

## Descripción del Proyecto
Este proyecto busca asesorar a una editorial en la optimización de su presupuesto de marketing mediante el análisis de datos de catálogos literarios (Goodreads). 

Para evitar decisiones basadas únicamente en la popularidad superficial, el análisis distingue entre la **Calidad percibida** (calificación promedio) y el **Alcance comercial** (volumen de reseñas), identificando títulos con alto potencial de crecimiento.

---

## Pregunta Principal de Negocio
> ¿Qué características permiten identificar libros con alto potencial de éxito y cuáles deberían ser priorizados por una editorial para invertir en marketing?

---

## Matriz de Caracterización del Éxito (Cuadrantes)
Dividimos el catálogo en 4 perfiles analíticos según las medianas de `average_rating` y `ratings_count`:

1. **Éxitos Consolidados:** Alta Calificación + Alto Volumen de Reseñas.
2. **Alto Potencial (Nicho a potenciar):** Alta Calificación + Bajo Volumen de Reseñas *(Target principal de marketing)*.
3. **Consumo Masivo:** Calificación Promedio/Baja + Alto Volumen de Reseñas.
4. **Bajo Desempeño:** Baja Calificación + Bajo Volumen de Reseñas.

---

## Hipótesis de Trabajo

1. **H1 - Extensión del libro:** Los libros de extensión media a larga (300 a 500 páginas) tienen una probabilidad significativamente mayor de pertenecer al perfil de *Alto Potencial* o *Éxitos Consolidados* que los libros de menos de 300 páginas.
2. **H2 - Reputación del Autor:** La presencia de un autor con un catálogo previo bien valorado reduce el tiempo/riesgo de conversión de un libro de *Alto Potencial* hacia un *Éxito Consolidado* al recibir pauta publicitaria.
3. **H3 - Ratio de Compromiso (Engagement Ratio):** El ratio de reseñas escritas sobre evaluaciones totales (`text_reviews_count / ratings_count`) es un predictor más sólido del perfil de *Alto Potencial* que la calificación promedio (`average_rating`) aislada.

---

## Pipeline de Limpieza y Transformación de Datos

El procesamiento de datos implementado en Python incluye:
* Eliminación de duplicados y registros nulos esenciales.
* Limpieza y formateo de fechas (`publication_date`) y cálculo de antigüedad del libro (`book_age_years`).
* Filtrado de inconsistencias (ej. libros con `num_pages <= 0`).
* **Ingeniería de Características:**
  * Categorización por rango de páginas (`page_range`).
  * Creación del ratio de compromiso (`review_ratio`).
  * Agrupación de métricas históricas por autor.

## KPIs:

## Hallazgos realizados:
1. 
2.
3.

## Cómo reproducir el análisis