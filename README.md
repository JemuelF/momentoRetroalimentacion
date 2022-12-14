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

Con el resultado de la matriz de confusión podemos ver que aunque nuestro modelo parecía ser bueno por el error tan bajo que teníamos, en realidad es un modelo que no sirve, ya que no es capaz de dar un valor positivo, ni verdadero, ni falso, por lo tanto nuestro modelo solo está dando valores negativos y dado a que hay más valores negativos en nuestro set de validación, pareciera ser bueno

## Conclusión de la comparación de ambos modelos
Podemos ver que aunque el modelo de regresión lineal parece ser bueno gracias a algunos indicadores como el del error y el porcentaje de predicciones acertadas, la matriz de confusión nos permite saber que no es bueno y es algo que se podía esperar, ya que no está diseñado para dar valores binarios. En cambio, nuestro modelo de clasificación es bueno y en la matriz de confusión podemos ver que sí llega a los valores positivos, aunque como se mencionó en el análisis individual del modelo, puede ser bueno o malo dependiendo del contexto en el que se use, el modelo es mejor que el de regresión lineal debido a que sí está diseñado para devolvernos valores binarios.

## Ahora trataremos de mejorar el modelo analizando el sesgo y la varianza
<img width="451" alt="image" src="https://user-images.githubusercontent.com/71990312/190496004-f0d6ac41-7df9-4a81-9e50-c25a11134936.png">
Podemos ver que tiene una varianza baja pero un sesgo no muy bajo, lo que significa que los resultados son estables pero no tan acertados, como en la siguiente imagen
<img width="124" alt="image" src="https://user-images.githubusercontent.com/71990312/190496242-071eb0f9-2731-4172-9300-ef20c239b83e.png">

## Modificaremos las variables de entrada del modelo
Agregamos la variable Nivel de glucosa, que en el mapa de calor también mostraba una ligera correlación pero no suficiente para agregarla al primer modelo

### Nueva función de costo
<img width="1043" alt="image" src="https://user-images.githubusercontent.com/71990312/190834364-15d5ac28-6cb1-43ec-84bf-682025a8711c.png">

### Nuevo entrenamiento
<img width="1021" alt="image" src="https://user-images.githubusercontent.com/71990312/190834381-1a8474c0-de26-4f7e-b6a4-173f44a60499.png">

### Nuevos errores 
<img width="940" alt="image" src="https://user-images.githubusercontent.com/71990312/190834390-e073ad28-256b-423e-aa1a-2a2bf49d5f43.png">
Podemos ver como los errores aumentaron

### Nueva efectividad
<img width="889" alt="image" src="https://user-images.githubusercontent.com/71990312/190834399-2d26f853-8881-41f6-a76a-cc6a842b8048.png">

### Nueva gráfica de matriz de confusión
<img width="537" alt="image" src="https://user-images.githubusercontent.com/71990312/190834412-374c2706-6310-4c26-b632-262ff734a993.png">

Podemos ver que el resultado es casi similar al del modelo anterior pero empeora ligeramente

<img width="572" alt="image" src="https://user-images.githubusercontent.com/71990312/190834445-01c39b56-9c65-4c66-b55b-0a7bd15a2696.png">

Ese rendimiento menor también lo podemos visualizar en el sesgo y la varianza

# Conclusión final

El modelo no mejoró por lo que nos podemos quedar con el primer modelo y asumir que el agregar nuevas variables no mejorará nuestro modelo


