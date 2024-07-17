# Ciencia-de-Datos

El objetivo de este proyecto es analizar un conjunto de datos que contiene métricas de rendimiento de jugadores de la NBA a lo largo de sus carreras, con el propósito de identificar si la carrera de un jugador superará los cinco años. Para lograr esto, se han seguido una serie de pasos sistemáticos que incluyen la selección y estandarización de las variables, la evaluación de correlaciones, la aplicación de pruebas estadísticas y la reducción de dimensionalidad mediante el Análisis de Componentes Principales (PCA), además de la aplicación de modelos de clasificación como Lazzy Classifier y Random forest.

En primer lugar, se seleccionaron las variables continuas del dataset para realizar análisis estadísticos y aplicar técnicas de reducción de dimensionalidad. Estas variables incluyen métricas como juegos jugados, minutos jugados, puntos por partido, rebotes, asistencias, entre otras. Posteriormente, se estandarizaron estas variables para garantizar que todas tengan la misma escala, facilitando comparaciones y análisis posteriores.

Se evaluó la correlación de Pearson entre las variables continuas para entender la relación lineal entre ellas. A continuación, se aplicó el test de Bartlett para determinar si las variables tienen suficiente correlación entre sí para aplicar PCA. El criterio de Kaiser se utilizó para determinar el número de componentes principales a retener, los cuales explican la mayor cantidad de varianza posible del dataset.

Finalmente, se aplicó PCA utilizando el número de componentes determinado por el criterio de Kaiser, generando un nuevo DataFrame con los componentes principales. Este proceso no solo reduce la dimensionalidad del dataset, sino que también facilita la visualización y el análisis posterior de los datos.

Este análisis proporciona una base sólida para futuras etapas del proyecto, que pueden incluir la aplicación de modelos predictivos y de clasificación para determinar la duración de la carrera de un jugador de la NBA basado en sus métricas de rendimiento.



Desarrollo del proyecto: 

Seleccionar Variables Continuas:
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

Se implementan dos modelos de clasificación Lazzy Classifier y Random forest y sus respectivas explicaciones:

LazyClassifier es una herramienta incluida en el paquete lazypredict, diseñada para simplificar el proceso de comparación de diferentes modelos de clasificación. Su objetivo principal es proporcionar una forma rápida y sencilla de evaluar múltiples algoritmos de clasificación sin necesidad de configuraciones complejas. LazyClassifier es especialmente útil en la etapa exploratoria de un proyecto de ciencia de datos, donde el objetivo es identificar rápidamente los modelos que tienen mejor rendimiento con el conjunto de datos proporcionado.

La apliación del modelo concluye que el mejor modelo es NearestCentroid con una precisión de 0.73

Resultados Random forest:

La precisión (accuracy) del modelo es del 72.93%. Esto significa que, en promedio, el modelo clasifica correctamente el 72.93% de las observaciones en el conjunto de prueba. La precisión general mide la proporción de predicciones correctas (tanto positivos como negativos) sobre el total de predicciones.

Precisión 
Para la clase 0 (jugadores con carreras de menos de 5 años), la precisión es de 66%. Esto significa que el 66% de las predicciones que el modelo hizo para esta clase fueron correctas.
Para la clase 1 (jugadores con carreras de más de 5 años), la precisión es de 77.11%. Esto indica que el 77.11% de las predicciones hechas para esta clase fueron correctas.

Recall (Sensibilidad o Tasa de Verdaderos Positivos)
El recall también se calcula para cada clase:
Para la clase 0, el recall es de 63.46%. Esto significa que el modelo identifica correctamente el 63.46% de los jugadores con carreras de menos de 5 años.
Para la clase 1, el recall es de 79.01%. Esto indica que el modelo identifica correctamente el 79.01% de los jugadores con carreras de más de 5 años.

Puntuación F1 (F1 Score)

La puntuación F1 es la media armónica de la precisión y el recall. Se calcula para cada clase:
Para la clase 0, la puntuación F1 es de 64.71%. Este valor combina la precisión y el recall para proporcionar una medida equilibrada del rendimiento del modelo en esta clase.
Para la clase 1, la puntuación F1 es de 78.05%. Este valor también combina la precisión y el recall para la clase de jugadores con carreras de más de 5 años.

Cohen's Kappa

Cohen's Kappa es una métrica que mide el acuerdo entre las predicciones del modelo y las clases reales, ajustando por el acuerdo que podría ocurrir por casualidad. Un valor de 0.4277 indica un nivel moderado de acuerdo más allá del azar. En otras palabras, el modelo es significativamente mejor que una clasificación aleatoria, pero todavía hay margen de mejora.

Conclusión

El modelo Random Forest ha mostrado un rendimiento razonable en la clasificación de la duración de la carrera de los jugadores de la NBA, con una precisión general del 72.93%. Sin embargo, hay diferencias en el rendimiento entre las clases. El modelo es más preciso y tiene un mayor recall para la clase 1 (jugadores con carreras más largas) en comparación con la clase 0. Esto podría indicar que el modelo está mejor ajustado para identificar jugadores que tienen carreras de más de 5 años. La puntuación F1 y el coeficiente de Cohen Kappa también sugieren que el modelo tiene un rendimiento moderadamente bueno, pero hay espacio para mejorar su capacidad de generalización y equilibrio entre las clases.
