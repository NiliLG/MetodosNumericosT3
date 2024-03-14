ELIMINACIÓN GAUSSSIANA

El método de eliminación de Gauss-Jordan se refiere a una estrategia utilizada para obtener la forma escalonada por filas de una matriz. 
El objetivo es escribir la matriz A A con el número 1 como entrada en la diagonal principal y con todos los ceros debajo.

Algoritmo
1. Paso de Eliminación hacia adelante:
  Para cada fila i desde 1 hasta n:
    Encuentra el máximo elemento en la columna i (incluida la fila actual) y llámalo pivote.
    Si el pivote es cero, no se puede continuar, ya que implica una división por cero.
    Intercambia la fila actual con la fila que contiene el pivote máximo, si es necesario.
    Para cada fila j desde i + 1 hasta n:
      Calcula el factor de eliminación como el elemento en la fila j, columna i dividido por el pivote.
      Resta factor * fila_i de la fila j, para hacer cero el elemento debajo del pivote.
2. Paso de Sustitución hacia atrás:
  Para cada fila i desde n hasta 1:
    Encuentra la solución de la ecuación correspondiente al término independiente.
    Resta los términos ya resueltos multiplicados por sus coeficientes correspondientes de la ecuación actual.
    Divide el término independiente por el coeficiente del término de la incógnita actual, para encontrar su solución.
3. Las soluciones encontradas representan las incógnitas del sistema de ecuaciones lineales original.

MÉTODO DE GAUSS-JORDAN

El método de Gauss-Jordan utiliza operaciones con matrices para resolver sistemas de ecuaciones de n numero de variables. Para aplicarlo solo hay que recordar que cada operación que se realice se aplicara a toda la fila o a toda la columna en su caso. Su objetivo es tratar de convertir la parte de la matriz donde están los coeficientes de las variables en una matriz identidad. Esto se logra mediante simples operaciones de suma, resta y multiplicación. 

Algoritmo
1. Paso de Eliminación hacia adelante:
  Para cada fila i desde 1 hasta n:
    Encuentra el máximo elemento en la columna i (incluida la fila actual) y llámalo pivote.
    Si el pivote es cero, no se puede continuar, ya que implica una división por cero.
    Intercambia la fila actual con la fila que contiene el pivote máximo, si es necesario.
    Para cada fila j desde 1 hasta n:
      Si j no es igual a i:
      Calcula el factor de eliminación como el elemento en la fila j, columna i dividido por el pivote.
      Resta factor * fila_i de la fila j, para hacer cero el elemento debajo del pivote.
2. Paso de Sustitución hacia atrás:
  Para cada fila i desde n hasta 1:
    Divide la fila i por el elemento en la posición (i, i) (el pivote), para hacer el pivote igual a 1.
    Para cada fila j desde 1 hasta n, si j no es igual a i:
      Resta fila_i * elemento_en_posicion(j, i) de la fila j, para hacer cero todos los elementos por encima del pivote en la columna i.
3. Las soluciones se encuentran en la última columna de la matriz reducida por filas.
