EQUIPO:
* Agis Mogollan Kate Michelle
* De Santiago Castillo Evelyn
* Alvarez Rivera Angel
* Hernández Zavala Gabriel
* López Gutiérrez Nili Estefanía


MÉTODO DE ELIMINACIÓN GAUSSSIANA

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

MÉTODO DE GAUSS-SEIDEL

El método de eliminación para resolver ecuaciones simultáneas suministra soluciones suficientemente precisas hasta para 15 o 20 ecuaciones. El número exacto depende de las ecuaciones de que se trate, del número de dígitos que se conservan en el resultado de las operaciones aritméticas, y del procedimiento de redondeo. Utilizando ecuaciones de error, el número de ecuaciones que se pueden manejar se puede incrementar considerablemente a más de 15 o 20, pero este método también es impráctico cuando se presentan, por ejemplo, cientos de ecuaciones que se deben resolver simultáneamente. El método de inversión de matrices tiene limitaciones similares cuando se trabaja con números muy grandes de ecuaciones simultáneas.

Algoritmo

1. Inicialización:
Dado un sistema de ecuaciones lineales Ax = b, descompón la matriz A en una suma de una matriz diagonal D, una matriz triangular inferior estricta L, y una matriz triangular superior estricta U, es decir, A = D + L + U.
Inicializa un vector de solución inicial x^(0) (por ejemplo, un vector de ceros).
2. Iteración:
Para cada iteración k = 1, 2, 3, ..., calcula el siguiente vector de solución x^(k) utilizando la siguiente fórmula:
x^(k)i = (1 / a(ii)) * (b_i - Σ_(j=1)^(i-1) a_(ij) * x^(k)j - Σ(j=i+1)^(n) a_(ij) * x^(k-1)_j)
Utiliza los nuevos valores de las incógnitas x^(k) para la próxima iteración.
3. Criterio de parada:
Selecciona un criterio de parada, por ejemplo, una tolerancia ε.
Si la diferencia entre dos iteraciones consecutivas ||x^(k) - x^(k-1)|| < ε, detén el proceso y devuelve x^(k) como solución aproximada.
4. Resultados:
La solución aproximada x^(k) es la solución del sistema de ecuaciones lineales.

MÉTODO DE JACOBI

Un método iterativo con el cual se resuelve el sistema lineal Ax = b comienza con una aproximación inicial x^(0)a la solución x y genera una sucesión de vectores x^(k) que converge a x. Los métodos iterativos traen consigo un proceso que convierte el sistema Ax = b en otro equivalente de la forma x = Tx + c para alguna matriz fija T y un vector c.

Algoritmo

1. Inicialización:
  Dado un sistema de ecuaciones lineales Ax = b, descompón la matriz A en una suma de una matriz diagonal D, una matriz triangular inferior estricta L, y una matriz triangular superior estricta U, es decir, A = D + L + U.
  Inicializa un vector de solución inicial x^(0) (por ejemplo, un vector de ceros).
  Calcula la inversa de la matriz diagonal D.
2. Iteración:
  Para cada iteración k = 1, 2, 3, ..., calcula el siguiente vector de solución x^(k) usando la siguiente fórmula:
  x^(k) = D^(-1) * (b - (L + U) * x^(k-1))
3. Criterio de parada:
  Selecciona un criterio de parada, por ejemplo, una tolerancia ε.
  Si la diferencia entre dos iteraciones consecutivas ||x^(k) - x^(k-1)|| < ε, detén el proceso y devuelve x^(k) como solución aproximada.
4. Resultados:
  La solución aproximada x^(k) es la solución del sistema de ecuaciones lineales.
