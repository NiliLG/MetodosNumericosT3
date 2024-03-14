Eliminación Gaussiana
El método de eliminación de Gauss-Jordan se refiere a una estrategia utilizada para obtener la forma escalonada por filas de una matriz. 
El objetivo es escribir la matriz A A con el número 1 como entrada en la diagonal principal y con todos los ceros debajo.
Algoritmo:

Entendido, aquí tienes el algoritmo de eliminación gaussiana:

Paso de Eliminación hacia adelante:

Para cada fila i desde 1 hasta n:
Encuentra el máximo elemento en la columna i (incluida la fila actual) y llámalo pivote.
Si el pivote es cero, no se puede continuar, ya que implica una división por cero.
Intercambia la fila actual con la fila que contiene el pivote máximo, si es necesario.
Para cada fila j desde i + 1 hasta n:
Calcula el factor de eliminación como el elemento en la fila j, columna i dividido por el pivote.
Resta factor * fila_i de la fila j, para hacer cero el elemento debajo del pivote.
Paso de Sustitución hacia atrás:

Para cada fila i desde n hasta 1:
Encuentra la solución de la ecuación correspondiente al término independiente.
Resta los términos ya resueltos multiplicados por sus coeficientes correspondientes de la ecuación actual.
Divide el término independiente por el coeficiente del término de la incógnita actual, para encontrar su solución.
Las soluciones encontradas representan las incógnitas del sistema de ecuaciones lineales original.
