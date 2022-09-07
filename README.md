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

## Entrenamiento del modelo
### Creamos nuestra función h y nuestra función de costo
<img width="1144" alt="image" src="https://user-images.githubusercontent.com/71990312/188995937-0bd951b1-662a-4355-b516-a7cdb46da3c7.png">

### Entrenamos nuestro modelo con un alpha de 5 y las tethas inicializadas en 1
<img width="1060" alt="image" src="https://user-images.githubusercontent.com/71990312/188996010-3e493827-5266-4519-8e82-b7ea9688b9d4.png">

### Revisamos el error de nuestro modelo
<img width="945" alt="image" src="https://user-images.githubusercontent.com/71990312/188996092-b6f1e656-6f63-4e66-911e-029f82962f7c.png">
El error con el set de entrenamiento es bastante bajo y con el set de validación sigue siendo bajo, por lo que podemos considerar nuestro modelo como uno bueno, ya que tiene balance, no existe ni underfitting ni overfitting.
A pesar de que este análisis nos sirve para justificar el modelo, revisaremos más información para darle mayor validez a nuestro modelo.

### Matriz de confusión
<img width="1099" alt="image" src="https://user-images.githubusercontent.com/71990312/188996240-1fd10ab6-d54b-46e6-94aa-2e9f2302ed32.png">

### Gráfica de predicciones correctas contra incorrectas
<img width="1011" alt="image" src="https://user-images.githubusercontent.com/71990312/188996294-85f9ac17-400a-4e85-8f89-2c4172fddb84.png">

### Gráfica de resultados de matriz de confusión
<img width="625" alt="image" src="https://user-images.githubusercontent.com/71990312/188996348-36f16d77-eee4-47ed-8a56-cef3704c4155.png">

