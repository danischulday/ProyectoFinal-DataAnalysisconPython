# Proyecto Final: Estrategia de Inversión Editorial basada en Data Analysis
Proyecto final para el Curso de Data Analysis con Python brindado por Comunidad IT.

## Descripción del Proyecto
Este proyecto busca recomendar a una editorial para lograr optimizar su presupuesto de marketing mediante el análisis de datos de catálogos literarios (Goodreads).

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

## Hallazgos realizados:
1. Criterio de Calidad Interno (El Estándar Goodreads)

    Hallazgo: La calificación promedio general se concentra entre 3.7 y 4.2 estrellas; el público casi no otorga puntajes bajos.

    Decisión de Negocio: Una nota de 3.8 no representa excelencia, sino la media del mercado. Para priorizar inversiones de marketing, el filtro mínimo de calidad debe fijarse en 4.1 o más estrellas.


2. Identificación de "Joyas Ocultas" vs. Bestsellers

    Hallazgo: Al cruzar calificación y cantidad de evaluaciones, surgen cuatro cuadrantes claros. Destaca un grupo de libros con calificaciones excelentes (4.2+) pero bajo volumen de evaluaciones (< 20.000).

    Decisión de Negocio: Estas "joyas ocultas" representan la oportunidad de mayor retorno de inversión (ROI) para la editorial, ya que cuentan con validación de calidad y solo requieren presupuesto de difusión para escalar en ventas.

3. Priorización por Género Literario

    Hallazgo: La concentración de títulos en el cuadrante de alto éxito no es uniforme; se agrupa fuertemente en un conjunto reducido de géneros masivos.

    Decisión de Negocio: Asignar la mayor proporción del presupuesto de marketing a los top géneros del mercado, asegurando una demanda base sólida y menor riesgo comercial.

4. La Extension Óptima del Libro ("Zona óptima")

    Hallazgo: La tasa de éxito comercial es menor en obras breves (< 200 páginas) y alcanza sus niveles más altos en libros de extensión media a alta (350 a 750 páginas).

    Decisión de Negocio: Al evaluar manuscritos para campañas de gran alcance, priorizar libros con desarrollo de contenido robusto (300+ páginas), ya que generan mayor compromiso y valor percibido por parte del lector.

5. El Peso de la Reputación del Autor (Reputación y Audiencia Previa)
    
    Hallazgo: Existe una diferencia estadísticamente significativa ($p < 0.001$) en la trayectoria previa de los autores. Los libros de "Alto Éxito" provienen de autores con una calificación previa promedio superior (4.06 vs. 3.90) y más del doble de popularidad previa acumulada (mediana de 5,757.5 vs. 2,807.0 evaluaciones) en comparación con el grupo de éxito bajo o medio.

    Decisión de Negocio: La reputación y la base de lectores establecida del autor son predictores sólidos del éxito comercial. Se debe establecer una estrategia diferenciada: destinar presupuestos de lanzamiento principales a autores con historial consolidado (rating previo $\ge 4.0$ y alta popularidad), mientras que para autores con menor tracción previa se deben implementar campañas de posicionamiento progresivas enfocadas en la construcción de su marca de autor.

## Supuestos y limitaciones

El conjunto de datos no incluye el texto completo de las reseñas u opiniones escritas por los lectores, limitándose a métricas cuantitativas (calificaciones numéricas, conteo de evaluaciones y popularidad). Si se contara con mayor tiempo, recursos o acceso a fuentes de datos complementarias, se podría seguir por una línea de trabajo que integre *Procesamiento de Lenguaje Natural (NLP)* para incorporar un análisis de sentimiento e identificación de temas clave sobre el texto de las reseñas escritas para comprender los factores cualitativos (trama, ritmo, desarrollo de personajes) que impulsan una calificación alta.

## Cómo reproducir el análisis

### Requisitos

- Python 3.x
- Jupyter Notebook o JupyterLab
- Pandas
- Matplotlib
- Seaborn
- Scipy
- Numpy

### Instalación

Clonar el repositorio:

```bash
git clone <https://github.com/danischulday/ProyectoFinal-DataAnalysisconPython.git>
cd <ProyectoFinal-DataAnalysisconPython.git>
```

Instalar las dependencias:

```bash
pip install pandas matplotlib seaborn scipy
```

Ejecutar Jupyter Notebook en orden:

```bash
jupyter notebook
```

---

# Tecnologías utilizadas

- **Python**
- **Pandas**
- **Scipy**
- **Numpy**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook**
- **Git / GitHub**

---

# Autora
- Daniela Espinoza
