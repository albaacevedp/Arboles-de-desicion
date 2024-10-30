# Arboles-de-desicion
Modelo de arboles de desicion y random forest sobre una base de datos de seguros que incluye las variables, edad, sexo, fuma, region e imc

Árbol de regresión
El árbol de regresión generado a partir de las variables edad, fuma, sexo, región, imc y edad para la variable gastos, y con los parámetros predeterminados genera 4 hojas, por lo que divide la variable gastos en los que gastan menos de 5578,  los que gastan entre 5578 y 12 651, los que gastan entre 12 651 y 21 543, los que gastan entre 21 543 y 41659,  y los que gastan más de 41 659.
 
Como se puede observar la variable que genera la primera división es si la persona fuma o no, generando un mayor gasto para quienes fuman, en el caso de no fumar la siguiente decisión se toma con base en la edad, a menor edad menor gasto, de la gente que fuma la siguiente decisión se toma con base en el imc, la gente con imc mayor a 30 genera más gastos en su seguro. En la siguiente tabla se presentan estas reglas de decisión.
 
Mediante la salida del modelo árbol de decisión podemos obtener el porcentaje de importancia de las variables para la construcción del árbol, el cual se muestra en la siguiente gráfica. En la que se puede observar que la variable de mayor importancia es la variable fuma, con un porcentaje de 69% de importancia, siguiendo imc con un porcentaje de 17% y la variable edad con un porcentaje de 9%. Qué son las tres variables con las que se construyo el modelo, ya que las variables, región, sexo y niños representan menos del 5%.  
 
Por último se uso el 20% de la base de datos como muestra de prueba, para observar el poder de predicción del modelo, y después se calculó la raíz del error cuadrático medio (RMSE), dando un valor de 4963.311. 
Para obtener el árbol de regresión con los parámetros qué nos dan el mejor árbol normalmente se ajustan los parámetros: mínimo número de observaciones por nodo (minsplit) y mínimo numero de observaciones en cada hoja (minbucket). De forma predeterminada son 20 y 7 respectivamente. Sin embargo, el árbol que se construyo en su nodo menor tiene 223 observaciones y en su hoja más pequeña 110. Qué no se hayan generado más ramificaciones tiene que ver con que de forma predeterminada el valor de la complejidad de costo optima es 0.01. Para obtener árboles más lo único que se puede hacer es hacer la complejidad de costo optimo menor.
Se construyo un árbol de decisión con una complejidad de costo optimo de 0.001, un nodo no menor a 200 y una hoja no menor a 100, y genero un árbol de 9 hojas, en las que para los seguros que generan mayor gasto singuen importando solo las variables fumar e imc. Para los seguros de menor gasto las variables que más influyen son no fumar y la edad, sin embargo ya se toman en cuenta las variables niños y región. Se obtuvo RMSE de las predicciones hechas sobre la base de datos de prueba y fue de 4892.29, lo cual representa un mejora de 0.01% sobre el 4963 obtenido con anterioridad. Debido a que la complejidad de costo optima ya era 0.01 obtener un árbol con un valor menor, haría poca diferencia sobre el poder de predicción. El árbol generado al inicio es un árbol con pocas ramificaciones por lo que podríamos decir que los datos presentaban nodos puros que predicen los datos mediante este modelo.

 
Para este árbol de regresión la tabla de reglas de decisión es la siguiente.

Random Forest
Se genero  un modelo de random Forest que de forma preliminar genera 500 árboles, la siguiente gráfica muestra como disminuye el error con el número de árboles, se observa una disminución rápida del error con forme aumentan los árboles empleados. El número de arboles en donde se encuentra el menor error es 312 con un RMSE de 4747.536. Lo cuál representa una mejora de 0.04% sobre el modelo de un solo árbol. La varianza explicada del modelo es del 84.57%. 
 
Mediante este modelo la predicción de los datos de muestra tiene un RMSE de 4565.424, que representa una mejora de 0.08% sobre el modelo de un solo árbol. 





