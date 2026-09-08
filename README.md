# ProyectoFinal-DataAnalysisconPython
Proyecto final para el Curso de Data Analysis con Python.

Descripción del proyecto
Mi objetivo como analista de datos es asesorar a una editorial en su decisión sobre en qué libros invertir marketing, pero para esto es necesario definir qué es lo que hace que un libro pueda ser exitoso. Existen por un lado libros que tienen un rating muy alto, pero una baja cantidad de reseñas (son poco conocidos) y también libros con miles de reseñas pero un rating más bien mediocre (populares, no necesariamente "buenos"). Entender esta diferencia nos ayudará a hacer mejores decisiones al momento de la inversión.

A tener en cuenta en el análisis:

* El sesgo entre Calidad y Popularidad: la relación entre la calificación promedio y el volumen total de reseñas para identificar qué libros son realmente apreciados por sus lectores versus aquellos que simplemente tienen un alto nivel de alcance.

* Caracterización del Éxito: analizando los distintos perfiles de libros presentes en el catálogo, diferenciando entre éxitos consolidados, productos de consumo masivo, títulos de nicho con alto potencial y libros de bajo desempeño.

* Patrones Directores: investigando si existen atributos en común dentro del catálogo (como la extensión del libro o las características del autor) que influyan en que un libro pase de ser un título poco conocido a un fenómeno de ventas.

* Criterios de Priorización de Inversión: formulación de un marco analítico para que la editorial pueda identificar cuáles son los títulos con mayor margen de crecimiento y retorno de inversión, optimizando así la asignación del presupuesto de marketing.

Pregunta principal
¿Qué características permiten identificar libros con alto potencial de éxito y cuáles deberían ser priorizados por una editorial para invertir en marketing?

Hipótesis iniciales
Las hipótesis que se manejan previo al análisis son las siguientes:
1. Extensión del libro
Los libros de extensión media a alta (entre 300 y 500 páginas) tienen una probabilidad mayor de pertenecer al grupo Alto Potencial o Éxitos Consolidados, en comparación con libros más cortos, ya que estos últimos suelen percibirse como menos "valiosos".
2. Reconocimiento del autor
Los libros ubicados en el perfil Alto Potencial cuyos autores poseen un historial previo bien valorado en otros títulos tienen un tiempo de conversión más rápido hacia Éxitos Consolidados al recibir pauta publicitaria, puesto que un autor con reputación positiva probada reduce el riesgo de inversión en publicidad, ya que el público que no conoce la obra específica sí confía en la marca personal del escritor.
3. Reseñas escritas
Una alta proporción de reseñas escritas sobre el total de evaluaciones (text_reviews_count / ratings_count) es un indicador más fuerte del perfil Alto Potencial que la calificación promedio (average_rating) por sí sola. Un lector que se toma el tiempo de redactar una reseña demuestra un nivel de lealtad y apasionamiento superior (efecto boca en boca), lo que hace que la inversión publicitaria sea más orgánica y eficiente.
