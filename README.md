# Ciencia-de-Datos

El objetivo de este proyecto es analizar un conjunto de datos que contiene métricas de rendimiento de jugadores de la NBA a lo largo de sus carreras, con el propósito de identificar si la carrera de un jugador superará los cinco años. Para lograr esto, se han seguido una serie de pasos sistemáticos que incluyen la selección y estandarización de las variables, la evaluación de correlaciones, la aplicación de pruebas estadísticas y la reducción de dimensionalidad mediante el Análisis de Componentes Principales (PCA).

En primer lugar, se seleccionaron las variables continuas del dataset para realizar análisis estadísticos y aplicar técnicas de reducción de dimensionalidad. Estas variables incluyen métricas como juegos jugados, minutos jugados, puntos por partido, rebotes, asistencias, entre otras. Posteriormente, se estandarizaron estas variables para garantizar que todas tengan la misma escala, facilitando comparaciones y análisis posteriores.

Se evaluó la correlación de Pearson entre las variables continuas para entender la relación lineal entre ellas. A continuación, se aplicó el test de Bartlett para determinar si las variables tienen suficiente correlación entre sí para aplicar PCA. El criterio de Kaiser se utilizó para determinar el número de componentes principales a retener, los cuales explican la mayor cantidad de varianza posible del dataset.

Finalmente, se aplicó PCA utilizando el número de componentes determinado por el criterio de Kaiser, generando un nuevo DataFrame con los componentes principales. Este proceso no solo reduce la dimensionalidad del dataset, sino que también facilita la visualización y el análisis posterior de los datos.

Este análisis proporciona una base sólida para futuras etapas del proyecto, que pueden incluir la aplicación de modelos predictivos y de clasificación para determinar la duración de la carrera de un jugador de la NBA basado en sus métricas de rendimiento.
Seleccionar Variables Continuas:

Desarrollo del proyecto: 

Se seleccionaron las variables continuas del dataset para realizar análisis estadísticos y aplicar técnicas de reducción de dimensionalidad. Las variables seleccionadas fueron: GP, MIN, PTS, FGM, FGA, FG%, 3P Mode, 3PA, 3P%, FTM, FTA, FT%, OREB, DREB, REB, AST, STL, BLK, y TOV.
Estandarización de Variables Continuas:

Para garantizar que todas las variables tengan la misma escala, se estandarizaron las variables continuas. La estandarización implica restar la media y dividir por la desviación estándar de cada variable. Esto genera un nuevo DataFrame con las variables estandarizadas, facilitando comparaciones y análisis posteriores.

El test de Bartlett se utilizó para determinar si las variables tienen suficiente correlación entre sí para aplicar PCA. La hipótesis nula del test de Bartlett establece que las variables no están correlacionadas. Un valor p bajo (<0.05) indica que podemos rechazar la hipótesis nula y proceder con el PCA. #Aplicando el indice de Barlet el p-value es 0, por lo que a cualquier nivel de significancia se rechaza la hipotesis nula. Por lo tanto existe una relacion entre las variables.
Determinación del Número de Componentes (Criterio de Kaiser):

Se determinó el número de componentes principales a retener utilizando el criterio de Kaiser, que sugiere retener los componentes con valores propios (eigenvalues) mayores a 1. Esto ayuda a reducir la dimensionalidad del dataset mientras se conserva la mayor cantidad de varianza posible.
Mostrar Varianza Explicada de los Componentes:

Se calculó y visualizó la varianza explicada por cada componente principal. Esto permite entender qué proporción de la varianza total del dataset es capturada por cada componente, ayudando a evaluar la eficacia del PCA.
Aplicación de PCA con Semilla 2021:

Se aplicó PCA utilizando el número de componentes determinado por el criterio de Kaiser. Para reproducibilidad, se fijó una semilla aleatoria (2021) durante el proceso de PCA. Se generó un nuevo DataFrame con los componentes principales, listos para su análisis posterior.

