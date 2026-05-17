# Trabajo Práctico 3 - Aprendizaje No Supervisado

## Descripción del trabajo

En este trabajo se aplicaron técnicas de aprendizaje no supervisado sobre un dataset relacionado con características fisicoquímicas del vino. 

El objetivo principal fue analizar la estructura de los datos utilizando reducción de dimensionalidad mediante PCA y técnicas de agrupamiento con K-means, comparando diferentes enfoques de clustering.

## Dataset utilizado

Se utilizó el dataset **WineQT**, obtenido de una fuente pública de datos. 

El conjunto de datos contiene variables numéricas relacionadas con propiedades químicas del vino, entre ellas:

- fixed acidity
- volatile acidity
- citric acid
- residual sugar
- chlorides
- free sulfur dioxide
- total sulfur dioxide
- density
- pH
- alcohol


## Técnicas aplicadas

Durante el desarrollo del trabajo se utilizaron las siguientes técnicas:

### Estandarización de datos
Las variables fueron escaladas utilizando `StandardScaler`, debido a que PCA y K-means son sensibles a las diferencias de escala.

### PCA (Análisis de Componentes Principales)
Se aplicó PCA sobre el dataset original con el objetivo de reducir dimensionalidad y analizar la varianza explicada por cada componente principal.

Además:
- se construyó un scree plot,
- se calculó la varianza acumulada,
- y se redujo el dataset a las 2 primeras componentes principales.

### Visualización
Se realizó un gráfico de dispersión utilizando las dos componentes principales para observar posibles agrupamientos visuales en los datos.

### Selección de variables
Se utilizó una matriz de correlación para identificar variables altamente correlacionadas y reducir redundancia en el dataset.

Como resultado, se eliminaron algunas variables consideradas redundantes.

### K-means
El algoritmo K-means fue aplicado sobre:

1. El dataset original
2. El dataset reducido mediante PCA
3. El dataset reducido mediante selección de variables

Para cada caso se evaluaron distintos valores de K entre 2 y 6 utilizando:
- Método del codo
- Silhouette score

## Principales hallazgos

- PCA permitió reducir la dimensionalidad manteniendo gran parte de la información del dataset.
- Las primeras componentes principales explicaron una proporción importante de la varianza total.
- El gráfico de dispersión mostró ciertos agrupamientos entre observaciones.
- La selección de variables ayudó a reducir redundancia entre características altamente correlacionadas.
- K-means presentó diferencias en el desempeño dependiendo de la versión del dataset utilizada.
- El silhouette score permitió comparar la calidad de los agrupamientos obtenidos.
