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

### Dividimos los datos en set de entrenamiento(60%), validación(20%),test(20%) de manera aleatoria
<img width="912" alt="image" src="https://user-images.githubusercontent.com/71990312/188990723-3fb7d0db-9f81-4d79-aef7-31e3b6fddc3f.png">

Hasta este momento, los pasos para los dos modelos que vamos a probar son iguales y a partir de aquí se toman caminos diferentes

## Entrenamiento del modelo
### Creamos nuestra función h y nuestra función de costo (Clasificación)
<img width="1144" alt="image" src="https://user-images.githubusercontent.com/71990312/188995937-0bd951b1-662a-4355-b516-a7cdb46da3c7.png">

### Creamos nuestra función h y nuestra función de costo (Regresión lineal)
<img width="960" alt="image" src="https://user-images.githubusercontent.com/71990312/189001379-7d0be743-1d36-48ea-bf31-f51dd132d30b.png">

### Entrenamos nuestro modelo con un alpha de 5 y las tethas inicializadas en 1 (Clasificación)
<img width="1060" alt="image" src="https://user-images.githubusercontent.com/71990312/188996010-3e493827-5266-4519-8e82-b7ea9688b9d4.png">

### Entrenamos nuestro modelo con un alpha de 0.1 y las tethas inicializadas en 1 (Regresión lineal)
<img width="1036" alt="image" src="https://user-images.githubusercontent.com/71990312/189001430-259771e0-be29-4e99-8117-b5f868410aab.png">


### Revisamos el error de nuestro modelo (Clasificación)
<img width="945" alt="image" src="https://user-images.githubusercontent.com/71990312/188996092-b6f1e656-6f63-4e66-911e-029f82962f7c.png">
El error con el set de entrenamiento es bastante bajo y con el set de validación sigue siendo bajo, por lo que podemos considerar nuestro modelo como uno bueno, ya que tiene balance, no existe ni underfitting ni overfitting.
A pesar de que este análisis nos sirve para justificar el modelo, revisaremos más información para darle mayor validez a nuestro modelo.

### Revisamos el error de nuestro modelo (Regresión lineal)
<img width="905" alt="image" src="https://user-images.githubusercontent.com/71990312/189001487-fa9b7b18-c794-4082-a7d3-c40e92f8c378.png">
El error en el set de entrenamiento y en el de validación es bastante bajo, por lo que podríamos considerar que es un buen modelo, pero aún tenemos que revisar la información completa que tenemos


### Matriz de confusión (Clasificación)
<img width="1099" alt="image" src="https://user-images.githubusercontent.com/71990312/188996240-1fd10ab6-d54b-46e6-94aa-2e9f2302ed32.png">

### Matriz de confusión (Regresión lineal)
<img width="1122" alt="image" src="https://user-images.githubusercontent.com/71990312/189001650-d6da730c-f647-439a-975d-12a34df58ac4.png">


### Gráfica de predicciones correctas contra incorrectas (Clasificación)
<img width="1011" alt="image" src="https://user-images.githubusercontent.com/71990312/188996294-85f9ac17-400a-4e85-8f89-2c4172fddb84.png">

### Gráfica de predicciones correctas contra incorrectas (Regresión lineal)
<img width="951" alt="image" src="https://user-images.githubusercontent.com/71990312/189001690-d8580a32-1673-4aa2-8fd6-4216a08156aa.png">


### Gráfica de resultados de matriz de confusión (Clasificación)
<img width="625" alt="image" src="https://user-images.githubusercontent.com/71990312/188996348-36f16d77-eee4-47ed-8a56-cef3704c4155.png">

Con el análisis de la matriz de confusión en conjunto con el error y el porcentaje de predicciones correctas, podemos ver que es un muy buen modelo para predecir cuando un paciente no tendrá un derrame, y es un modelo aceptable para cuando un paciente sí tendrá un derrame, dependiendo de en que casos de uso se necesite el modelo puede que esto sea algo bueno o que se requiera modificar el modelo

### Gráfica de resultados de matriz de confusión (Regresión lineal)
<img width="523" alt="image" src="https://user-images.githubusercontent.com/71990312/189001742-cdab2aeb-3bda-49ff-920f-5cb58b8c6f7c.png">

