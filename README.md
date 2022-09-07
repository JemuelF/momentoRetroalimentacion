# momentoRetroalimentacion

El repositorio completo puede correr en local, igual se puede correr en el collab

El código se encuentra comentado con la información necesaria para saber como funciona el modelo

[ Link al collab ](https://colab.research.google.com/drive/1J5ScgFSZOeeDR6j1FcuKWXWncWn-SI7V?usp=sharing)

## Descripción de dataset
Para este análisis se utilizará un dataset que contiene información de pacientes y si han sufrido un derrame o no

## Objetivo
El objetivo de mi análisis es comparar dos modelos diferentes para un mismo dataset, los modelos serán un algoritmo de clasificación y un algoritmo de regresión lineal forzado a generar valores binaros, para ver las diferencias entre uno y otro

## Limpieza del dataset
### Transformamos la variable smoking_status a una variable dummy para poder realizar un correcto análisis de la misma
<img width="496" alt="image" src="https://user-images.githubusercontent.com/71990312/188988667-acba2d7f-fa7e-4ec7-be1c-8b85abde2dac.png">

### Transformamos la variable de tipo de residencia para poder analizarla
<img width="796" alt="image" src="https://user-images.githubusercontent.com/71990312/188989230-e0d24fa9-72c9-4dd3-964a-42f6558fe5d8.png">

### Se utiliza un mapa de calor para revisar la correlación de las variables con la variable resultado
<img width="939" alt="image" src="https://user-images.githubusercontent.com/71990312/188989283-973acb33-285f-4613-88b1-56921ff6613a.png">

### Eliminamos las variables que no serán de utilidad para nuestro modelo
<img width="273" alt="image" src="https://user-images.githubusercontent.com/71990312/188989417-14e39d7e-f135-4d8b-82f6-4b0de141f02b.png">

### Revisamos el mapa de calor con las variables finales
<img width="419" alt="image" src="https://user-images.githubusercontent.com/71990312/188989557-8e5ebc1b-1356-42a3-beca-33c19ab02eb1.png">


